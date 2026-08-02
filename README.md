# Water segmentation on Sentinel-2 with TorchGeo

Segmentazione per classificazione binaria acqua / non-acqua su immagini Sentinel-2, a partire dal
dataset [Earth Surface Water](https://huggingface.co/datasets/cordmaur/earth_surface_water).

Il punto di partenza è il [tutorial TorchGeo](https://docs.torchgeo.org/en/stable/tutorials/earth_surface_water.html),
esteso con verifiche geospaziali preliminari, valutazione su immagini intere
e un confronto tra due configurazioni di input.

## Risultati

| Per pixel | A (9 canali) | B (3 indici) |
|---|---|---|
| Precision | 0,9339 | **0,9720** |
| Recall | 0,7705 | **0,7986** |
| F1 | 0,8444 | **0,8768** |
| FP su non-acqua | 1,06 % | **0,45 %** |

| Per immagine (su 31) | A | B |
|---|---|---|
| Accettabili | **11** | 8 |
| Nessun pixel predetto | **0** | 3 |

Dettagli e discussione in [`report/report.pdf`](report/report.pdf).

![Confronto qualitativo](figures/confronto_B.png)

## Come eseguire

```bash
pip install -r requirements.txt
jupyter notebook notebooks/water_segmentation.ipynb
```

Il dataset viene scaricato dal notebook. Il training richiede una GPU
(testato su Colab, T4).

## Dati e attribuzioni

- Dataset: Earth Surface Water, licenza CC BY 4.0
- Codice di partenza: tutorial TorchGeo

## Licenza

MIT per il codice, CC BY 4.0 per il report. Vedi [LICENSE](LICENSE).
