# Probing Transformer Layers for Syntactic Structure

# Project goal
This project investigates how syntactic information, specifically dependency relations, is represented across the layers of a pretrained BERT model. I use supervised probing experiments to examine how effectively dependency relations can be predicted from frozen BERT representations.

# Research Questions

1. How accurately can dependency relations be predicted from different layers of pretrained BERT?

2. Which BERT layers provide the most useful representations for dependency relation prediction?

3. Does incorporating the representation of a word's syntactic head improve dependency relation prediction compared with using only the dependent word's representation?


# Dataset and Model

Dataset: Universal Dependencies English-EWT

Model: bert-base-uncased

Architecture: 12-layer pretrained BERT

Task: Dependency relation classification

Probing classifier: Logistic Regression

Baseline: DummyClassifier using the most frequent class strategy

# Experimental Methodology

The experiments follow these steps:

Load and explore the Universal Dependencies English-EWT dataset.

Tokenize sentences using the BERT tokenizer and align WordPiece tokens with their original words.

Extract hidden representations from all 12 BERT layers while keeping the pretrained BERT model frozen.

Construct two feature configurations:

Dependent-only: Use the representation of the dependent word.

Head+dependent: Concatenate the representations of the dependent word and its syntactic head.

Train Logistic Regression probes using the extracted representations.

Compare the probes against a majority-class baseline.

Evaluate performance using accuracy and macro-F1.

Compare layer-wise results and analyze the findings and limitations.



# Project Structure

README.md : Project overview, research questions, methodology, and documentation.

src/ : Jupyter notebooks containing the project implementation.

dataset_exploration.ipynb : Dataset exploration, BERT representation extraction, dependency relation probing, and evaluation.

environment_check.ipynb : Environment and library configuration checks.

# Scope and Limitations

The experiments focus on English dependency relations using the English-EWT dataset.

Only the pretrained bert-base-uncased model is investigated.

BERT parameters remain frozen during the probing experiments.

Logistic Regression probes evaluate the syntactic information accessible to a linear classifier; their performance does not directly demonstrate how BERT internally processes or uses syntax.

The findings are limited to the selected model, dataset, and experimental setup.

