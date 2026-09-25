# Multimodal Recipe Extractor
### B.Sc Deep Learning Course Project
## Overview
This project was developed as part of a B.Sc. Deep Learning course. It implements a multimodal system that combines computer vision and large language models to recognize food from an input image and generate an appropriate recipe.

The system consists of two main stages:
1. Food Recognition – A fine-tuned ResNet-50 convolutional neural network (CNN) analyzes an input image and predicts the top 3 most likely food classes.
2. Recipe Generation – The top 3 predictions are provided as context to a LLaMA 2 7B language model, which generates a recipe corresponding to the identified food.

## Dataset
The image classification component was trained using the Food-101 dataset, which contains images belonging to 101 different food categories.

The project also uses a recipe dataset containing information such as food/recipe labels, ingredients and the recipe instructions.

## Models
### ResNet-50
A pretrained ResNet-50 model was used as the base image classification model. The model was adapted and fine-tuned for the Food-101 classification task.
The image classifier produces a probability distribution over the food classes, from which the three highest-probability predictions are selected.

### LLaMA 2 7B
The top 3 predictions from the image classifier are passed to a LLaMA 2 7B language model. The model uses these predictions to generate a suitable recipe.
Additional example recipes are included in the prompt to provide the model with additional context and encourage creative while reasonable recipe generation.

## Project Notebook
The main project notebook (.ipynb) contains the complete development and experimentation process.

Important: The notebook is intentionally structured to document our work process, rather than being presented as a clean, production-ready implementation.
As required by the course submission guidelines, the notebook demonstrates the different stages of development, experimentation, model training, evaluation, and testing. As a result, it may contain:

* Repeated or redundant code
* Multiple versions of experiments
* Intermediate results
* Training attempts and evaluations
* Code that was later replaced or modified
* Explanations of decisions made throughout the development process

Some cells may therefore appear unnecessary when viewed purely as a final implementation. They are included intentionally to provide a transparent record of our development process and to demonstrate the reasoning and experimentation behind the final system.

## Technologies
* Python
* PyTorch
* Torchvision
* ResNet-50
* LLaMA 2 7B
* Hugging Face Transformers
* Food-101
* Jupyter Notebook / Google Colab

## Project Structure
```text
.
├── README.md
└── DLProjectMRE.ipynb
```
The main `.ipynb` notebook contains the implementation, experiments, training procedures, evaluation, and final demonstration.

## Results
The ResNet-50 classifier achieved the following results on the Food-101 classification task:
| Metric | Result |
|---|---:|
| Top-1 Accuracy | 74.52 % |
| Top-3 Accuracy | 87.75 % |
| Precision | 74.62 % |
| Recall | 74.52 % |
| F1 Score | 74.44 % |

The top-3 classification approach was used because providing multiple candidate food classes to the language model allows the recipe-generation stage to make use of the classifier's highest-confidence predictions.

## LLM Assistance
Note: ChatGPT was used as a development aid for portions of the code, including code generation and debugging. All generated code was reviewed and adapted by the authors.

## Authors
Lidor Lutati - lidor37@gmail.com - [GitHub: LL37477](https://github.com/LL37477)
Haim Bortman - bortman.haim@gmail.com - [GitHub: hb9111](https://github.com/hb9111)
