# Thai-Coref
Coreference Resolution for Thai using neural end-to-end models

## Introduction
This repository contains the code from
- [Higher-order Coreference Resolution with Coarse-to-fine Inference](https://arxiv.org/abs/1804.05392)
- [End-to-end Neural Coreference Resolution](https://arxiv.org/abs/1707.07045)
- [20MinsNLP 20190402-Coreference](https://colab.research.google.com/drive/16hxZTrJS-yvgdeTspDKju2dsVV-TyPY9)

Coreference resolution is considered as an important natural language processing task helping us improve model performance more effectively by learning and understanding what actually the tokens is referred to in the text.<p>
In the NLP history, many experts have tried the Coreference resolution in both rule-based model and learning-based model such as Mention-pair model, Mention ranking model, entity pair model or the state-of-the-art neural network model for instance End-to-end neural coreference resolution model and also BERT Language model that used to encode language information. To add to it, the later models were developed to fix the problems found in the previous ones.



## Methodology
In our experiment with Thai data, we use 2 models which are End-to-end neural coreference resolution from kenton L 2017 and Higher-Order Coreference Resolution with Coarse-to-Fine Inference from Kenton L 2018. These 2 models  joint 2 sub models together which are Mention detection model and coreference detection model and we also use  the other resources of data from thai national corpus, word embedding and other features. 



## Dataset
Input data: labeled data from Thai national corpus and Wikipedia total of 915 documents <br>
Training set : 732 documents<br>
Validation set : 91 documents<br>
Test set : 92 documents<br>



## Experiment setup
Embeddings : TNC word embeddings with 200 dimensions<p>
Due to the lack of ram, we use considerably less hyperparameters than in the paper. We limit the max antecedents to 50 in e2e-coref and 35 in c2f-coref (from 250 max antecedents) and due to the lack of time, we train the model only 75 epochs (from 150 epochs) which took more than 23 hours. Hence, the results turned out to be quite poor especially the recall result.


## Results


## Model comparison
|   |Precision     | Recall| F1|
| ----------- |-----------| -----------|-----------|
| e2e-coref     | 31.95 |  7.79 |  12.478 |
| c2f-coref  |    45.24     |4.68|8.41|
| e2e-coref w/ oracle mention  |   70.46  |60.59|64.82|



## Conclusion
The Coarse-to-fine Model performs better overall than the previous one due to the further algorithm for dealing with a span that is not a mention even though the antecedents were aggressively pruned. However, the catch is more computational resource usage.<p>
Nevertheless, working with Thai data has more limitations than working with English one (The CoNLL-2012) because we don't have some features that have the potential to improve the models such as character embeddings, contextualized embeddings, or metadata.

## Future Work
- More training data
- Tuning hyperparameters
- Replacing BiLSTM encoder with BERT!
- Trying with other interesting models e.g. CorefQA, SpanBERT