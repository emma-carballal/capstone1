# Sentiment classification with a transformers model
## A Captstone 1 project for the DataTalksClub ML Zoomcamp
The purpose of this project is to fine-tune a pretrained transformer model with a sentiment classification dataset, create a lambda function, containerize it and and deploy it to AWS Lambda.

### Description
The pretrained model selected for finetuning is the [BERT base model (uncased)](https://huggingface.co/bert-base-uncased) from Hugging Face. BERT is a transformers model pretrained on a large corpus of English data in a self-supervised fashion. It was pretrained for masked language modelling and next sentence prediction, but here we'll fine-tune it for a sentiment classification task.

The pretrained model selected for finetuning is the [BERT base model (uncased)](https://huggingface.co/bert-base-uncased) from Hugging Face. BERT is a transformers model pretrained on a large corpus of English data in a self-supervised fashion. It was pretrained for masked language modelling and next sentence prediction, but here we'll fine-tune it for a sentiment classification task.

The dataset selected to fine-tune the pretrained model is GLUE, available in the [Hugging Face Dataset Hub](https://huggingface.co/datasets). GLUE stands for [General Language Understanding Evaluation benchmark](https://gluebenchmark.com/), and is a collection of resources for training, evaluating, and analyzing natural language understanding systems.
For the task at hand, the subset 'sst2' is used. The Stanford Sentiment Treebank (sst2) consists of sentences from movie reviews and human annotations of their sentiment.

The raw dataset is already split into `train`, `validation` and `test`:
```
DatasetDict({
    train: Dataset({
        features: ['sentence', 'label', 'idx'],
        num_rows: 67349
    })
    validation: Dataset({
        features: ['sentence', 'label', 'idx'],
        num_rows: 872
    })
    test: Dataset({
        features: ['sentence', 'label', 'idx'],
        num_rows: 1821
    })
})
```
The structure of the data in the train split is a dictionary with a `sentence`, a `label`(0: negative, 1: positive) and an `index`:

```
{'sentence': 'goes to absurd lengths ', 'label': 0, 'idx': 10}
````
