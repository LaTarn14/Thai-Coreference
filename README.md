# Thai-Coreference
Thai Coreference using end-to-end model

## Introduction
<<<<<<< HEAD
Coreference resolution is considered as an important nlp task helping us improve model performance more effectively by learning and understanding what actually the tokens is referred to in the text.

In the NLP history, many experts have tried the Coreference resolution in both rule-based model and learning-based model such as Mention-pair model, Mention ranking model, entity pair model or the state-of-the-art neural network model for instance End-to-end neural coreference resolution model and also BERT Language model that used to encode language information. To add to it, the later models were developed to fix the problems found in the previous ones.

=======
ในบรรดา NLP downstream task Coreference resolution หรือการหาความหมายถึงสิ่งเดียวกันในโลก ถือเป็น subtask ที่มีความสำคัญ task หนึ่ง Coreference resolution เป็น task ที่จะช่วยให้โมเดลของเราสามารถทำงานได้มีประสิทธิภาพมากขึ้นจากการที่สามารถเรียนรู้และเข้าใจความหมายของคำอย่างแท้จริง 
ในประวัติศาสตร์ NLP ที่ผ่านมา มีผู้เชี่ยวชาญมากมายได้ทดลองการทำหลายรูปแบบ ทั้ง rule-based และ learning-based เช่น Mention-pair model, Mention ranking model, entity pair model หรือโมเดลที่ใช้ neural network เข้ามาช่วย เช่น End-to-end neural coreference resolution model 

What other people have done? What model have previous work have used? What did they miss? (1-2 paragraphs)
Summarize your idea
Summarize your results
>>>>>>> 9f58a6a74a38274e214bc294b4e57c932b367400

## Approach/Methodology/Model
In our experiment with Thai data, we use 2 models  which are End-to-end neural coreference resolution from kenton L 2017 and Higher-Order Coreference Resolution with Coarse-to-Fine Inference from Kenton L 2018. These 2 models  joint 2 sub models together which are Mention detection model and coreference detection model and we also use  the other resources of data from thai national corpus, word embedding and other features. 



## Dataset
Input data: labeled data from Thai national corpus and Wikipedia total of 915 documents 
Training set : 732 documents
Validation set : 91 documents
Test set : 92 documents



## Experiment setup
Embeddings : TNC word embeddings with 200 dimensions

Due to the lack of ram, we use considerably less hyperparameters than in the paper. We limit the max antecedents to 50 in e2e-coref and 35 in c2f-coref (from 250 max antecedents) and due to the lack of time, we train the model only 75 epochs (from 150 epochs) which took more than 23 hours. Hence, the results turned out to be quite poor especially the recall result.


## Results
|   |Precision     | Recall| F1|
| ----------- |-----------| -----------|-----------|
| e2e-coref     | 31.95 |  7.79 |  12.478 |
| c2f-coref  |         |||

### Model comparison
| Model | Accuracy

## Conclusion
