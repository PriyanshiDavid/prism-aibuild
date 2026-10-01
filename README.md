# Prism: AI-assisted anomaly prioritisation

**AIBUILD Challenge 1, Launch Melbourne 2026**

Prism turns thousands of operational readings into a short, ranked to-do list, with a plain-English reason and a suggested next step for every item.

**Live prototype:** open `index.html`, or visit the GitHub Pages link for this repository.

## What's here

| Path | What it is |
|---|---|
| `index.html` | The prototype. A single self-contained web page; the model runs in the browser. |
| `notebook/AIBUILD_Project_revised.ipynb` | Analysis notebook: model development, benchmarking, holdout check, false-positive analysis. |
| `samples/machine_sample.csv` | 300 machine readings with an importance column, for the "Check your own data" tab. |
| `samples/logistics_sample.csv` | 1,000 synthetic delivery runs with five planted problems, showing Prism works beyond machines. |

## How it works

1. **Learn normal:** Prism learns what normal operation looks like from historical readings, with no breakdown labels needed (unsupervised machine learning: Mahalanobis distance).
2. **Rank:** every reading lands in one of four levels: check now, check today, keep an eye, routine. Critical assets move up a level, and spares move down.
3. **Explain:** each flag gets a plain-English reason and a next step.

## Results (AI4I 2020 dataset, labels used only for evaluation)

- 17 of the top 20 ranked machines really broke down (a random pick finds fewer than 1)
- 68% fewer alerts than one-sensor alarms, with twice the share of real breakdowns
- 81% of the top-100 false alarms were operating within 10% of a failure limit

## Data

The notebook uses the public [AI4I 2020 Predictive Maintenance Dataset](https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset) from the UCI Machine Learning Repository. Download `ai4i2020.csv` from there to re-run the notebook. The delivery sample is synthetic, generated for this prototype.

## Team

 Ibrahim Duwila, Priyanshi David, Heidy Wandurraga, Oyku Madenci, Alicia, 
