# Adversarial Natural Language Inference

This repository contains the code and resources for a Natural Language Inference (NLI) project that focuses on improving model robustness through data augmentation techniques. The project involves fine-tuning a pre-trained **roberta-base** model on a dataset with imbalanced classes and evaluating its performance on both original and adversarial test sets. Data augmentation techniques, such as Word Sense Disambiguation (WSD) and Semantic Role Labeling (SRL), are employed to enhance the dataset's volume and complexity, aiming to improve the model's generalization capabilities.

## Project Overview

The goal of this project is to develop an efficient and effective approach for analyzing data from different sources, particularly in the context of NLI tasks. The dataset includes premises, hypotheses, and labels (ENTAILMENT, NEUTRAL, CONTRADICTION). The original training set is imbalanced, while the test sets (original and adversarial) are balanced. The project explores how data augmentation can mitigate issues such as model overreliance on specific training patterns and improve performance on adversarial examples.

### Key Features:

- **Fine-tuning**: The **roberta-base** model is fine-tuned on the dataset using a batch size of 16, a learning rate of 1e-4, and weight decay of 0.001.
- **Data Augmentation**: Various augmentation techniques are applied to the dataset, including:
  - **WSD Augmentations**: Replacing nouns in hypothesis sentences using WordNet synsets.
  - **SRL Augmentations**: Manipulating semantic roles (e.g., swapping agent and patient roles, changing time references).
  - **Number-to-Text Conversion**: Replacing numerical values with their textual equivalents.
- **Evaluation**: The model's performance is evaluated on both original and adversarial test sets using metrics such as accuracy, precision, recall, and F1 score.

## Repository Structure

**Notebook**: The main code is contained in a single `.ipynb` notebook, which includes:

- Data loading and preprocessing.
- Model fine-tuning and training.
- Data augmentation techniques.
- Evaluation on original and adversarial test sets.

## Dataset

The dataset consists of the following keys:

- **id**: Unique identifier for each sample.
- **premise**: The premise used in the sample for the NLI task.
- **hypothesis**: The hypothesis used in the sample for the NLI task.
- **label**: The relationship between the premise and hypothesis (ENTAILMENT, NEUTRAL, CONTRADICTION).
- **wsd**: Word sense disambiguation information for both the premise and hypothesis.
- **srl**: Semantic role labeling information for both the premise and hypothesis.

## Results

The model's performance is evaluated on both the original and adversarial test sets. The results show that while the model performs well on the original test set, it struggles with adversarial examples. Data augmentation techniques help improve performance on the adversarial set, though there is still room for further enhancement.

### Performance Metrics:

- **Original Test Set**:
  - Accuracy: 0.74
  - Precision: 0.73
  - Recall: 0.74
  - F1: 0.73
- **Adversarial Test Set**:
  - Accuracy: 0.59
  - Precision: 0.59
  - Recall: 0.59
  - F1: 0.59

## How to Use

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/alighasemi78/Adversarial-Natural-Language-Inference.git
   cd Adversarial-Natural-Language-Inference
   ```

2. **Open the Notebook**:

   - Open the `.ipynb` notebook in Jupyter or any compatible environment.
   - Run the cells to load the data, fine-tune the model, apply data augmentation, and evaluate the results.

3. **Explore the Data**:

   - The dataset is loaded in the notebook, and you can explore the premises, hypotheses, and labels.
   - The augmentation techniques are detailed in the notebook, and you can modify or extend them as needed.

4. **Evaluate the Model**:
   - After training, the model's performance is evaluated on both original and adversarial test sets.
   - You can experiment with different augmentation techniques or hyperparameters to improve the results.

## References

- Michail Mersinias and Panagiotis Valvis. 2022. Mitigating dataset artifacts in natural language inference through automatic contextual data augmentation and learning optimization. In _Proceedings of the Thirteenth Language Resources and Evaluation Conference_, pages 427–435, Marseille, France. European Language Resources Association.
