# nlp-noise-robustness

This repository contains the code used for SIT770 Natural Language Processing Tasks 2.2D and 2.3HD.

The file `2_2D.ipynb` contains the SNIPS robustness experiment used in the Distinction task. It trains a clean DistilBERT-based joint intent-slot model and evaluates it on clean and noisy SNIPS test sets.

The experiment reports:
- intent accuracy
- slot F1
- semantic frame accuracy
- robustness drop

The included CSV and graph show the final results used in the 2.2D paper.
