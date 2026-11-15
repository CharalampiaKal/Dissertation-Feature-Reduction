# Progressive Feature Reduction for Network Intrusion Detection

This master's dissertation examines how reducing the number of input features affects a model's ability to distinguish normal network traffic from attacks. It asks whether a model can keep a similar overall score while missing more records from specific attack categories.

## Data and method

The study uses two datasets: [corrected CICIDS2017](https://intrusion-detection.distrinet-research.be/CNS2022/Dataset_Download.html) and [RT-IoT2022](https://archive.ics.uci.edu/dataset/942/rt-iot2022). It compares Logistic Regression, Random Forest, and XGBoost with full and reduced feature sets. Feature sets were selected using validation data, and the final comparisons used separate held-out test sets.

## Main finding

On the held-out test sets, five of six reduced configurations stayed within the overall Macro-F1 tolerance, but only two also stayed within the recall tolerance for every attack category.

For CICIDS2017 Logistic Regression, reducing the feature count from 82 to 58 lowered Macro-F1 by only 0.000935. Yet the model detected 167 rather than 189 of 261 DoS Slowhttptest records: 22 additional misses and an 8.43 percentage point drop in recall.

## Notebook

[Dissertation_Kalyva.ipynb](Dissertation_Kalyva.ipynb) contains the code, saved results, and figures. The checkpoint cells were used to resume long Colab runs and depend on files from the original Google Drive workspace. Those files are not included in this repository, so running every cell in order requires adapting the checkpoint sections.
