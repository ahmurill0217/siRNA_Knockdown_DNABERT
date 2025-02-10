# DNABERT6 siRNA Knockdown Prediction

# Overview
This project fine-tunes the DNABERT6 model to predict siRNA knockdown efficiency on target mRNA sequences. By leveraging the pre-trained DNABERT6's understanding of DNA/RNA sequence patterns, I have adapted it to learn the complex relationships between 21-nucleotide siRNA sequences and their corresponding mRNA targets.

There are many ways to approach the fine-tuning of DNABERT6 for an siRNA knockdown prediction task. This project is a proof of concept for a particular approach in which the both the siRNA and mRNA sequences are individually encoded via BERT and then concatenated. The concatenated sequences are then passed through the regression head to predict the knockdown efficiency.

# Architecture

The base model is DNABERT6 in which the pooler layers are unfrozen for fine-tuning. A regression head is added to the model to predict the knockdown efficiency.


# Dataset
The dataset is a collection of 2431 siRNA sequences, their corresponding mRNA targets, and their knockdown efficiency. The dataset is split into a training, test set, and validation set in a 70/15/15 ratio.

# Results
The model achieves a Pearson correlation coefficient of 0.6 on the validation dataset.
![alt text](model_training_metrics/best_model_3/best_model_3_training_metrics.png)


Additional, the model achieves a Pearson correlation coefficient of 0.53 on the test set (a never before seen dataset).
![alt text](model_training_metrics/best_model_3/best_model_3_testset_results.png)


