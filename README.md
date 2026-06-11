# NLP Noise Robustness

This repository contains the code and output files used for SIT770 Natural Language Processing Tasks 2.2D and 2.3HD.

The project studies the robustness of joint intent classification and slot-filling models under imperfect user input. It uses the SNIPS joint intent-slot dataset and a DistilBERT-based joint model.

## Task 2.2D: SNIPS Robustness Experiment

The file `2_2D_TASK.ipynb` contains the SNIPS robustness experiment used in the Distinction task.

This notebook trains a clean DistilBERT-based joint intent-slot model on clean SNIPS training data and evaluates it on:

- clean SNIPS test data
- misspelling noise
- punctuation/casing noise
- abbreviation/substitution noise
- mixed noise

The experiment reports:

- intent accuracy
- slot F1
- semantic frame accuracy
- robustness drop, reported as intent drop, slot F1 drop, and semantic frame drop

The included CSV and graph show the final results used in the 2.2D paper:

- `2_2D_snips_noise_robustness_results.csv`
- `2_2D_snips_noise_robustness_plot.png`

## Task 2.3HD: Noise-Aware Augmentation Experiment

The file `2_3HD_noise_augmented_SNIPS.ipynb` contains the High Distinction task experiment.

This notebook builds on the limitation identified in Task 2.2D: the clean-trained model performs strongly on clean input but loses slot-level and full semantic frame accuracy under noisy input.

The proposed solution is noise-aware data augmentation. The method keeps the original clean SNIPS training examples and adds one controlled noisy version of each training example. The noisy examples use token-preserving transformations so that the BIO slot labels remain aligned.

The augmented model is trained using the same DistilBERT-based joint intent-slot architecture and is compared against a clean-trained DistilBERT baseline.

The experiment evaluates both models on:

- clean SNIPS test data
- misspelling noise
- punctuation/casing noise
- abbreviation/substitution noise
- mixed noise

The evaluation reports:

- intent accuracy
- slot F1
- semantic frame accuracy
- robustness drop
- direct improvement from the baseline model to the noise-augmented model


```
