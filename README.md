Exploring A Data-Driven Method to Validate Rhetorical Structure Theory
===
Rhetorical Structure Theory (RST) is an explanatory theory for discourse parsing that has been extensively used in natural language computing research. RST characterizes texts by assigning relations to adjacent text units known as elementary discourse units (EDUs). However, there are several issues that have been brought up regarding RST. For example, segmenting discourse into EDUs might be problematic for some research problems and text span pair can belong to multiple relations, leading to ambiguity in discourse structures. In [this paper](http://shagungupta.net/files/NLP_Project.pdf), we investigate the validity of the RST framework for discourse parsing using a data-driven approach. We use the RST discourse Treebank (RST-DT) to examine the relatability between adjacent EDU pairs within a text and whether RST relations can be predicted objectively given a pair of EDUs. We do this by leveraging [BERT](https://arxiv.org/abs/1810.04805), a pre-trained deeply bidirectional, unsupervised language representation model. We find that most EDU pairs are highly related, while a smaller fraction seems to be very poorly related. In addition, the using EDU pairs for relation classification showed high variability with more common relation classes performing better. Our work demonstrates that RST can be subjective in nature and that further work should re-evaluate discourse segmentation and define better boundaries for RST relation classes.

## File Descriptions 

Task 1: Next EDU Prediction
- 1 Next EDU Preprocessing.ipynb: preprocessing RST-DT to generate adjacent EDU pairs
- 2 Next EDU Prediction.ipynb: runs BertForNextSentencePrediction Model
- 3 Next EDU Prediction Analysis.ipynb: analysis/plots for next EDU prediction

Task 2: RST Relation Classification
- For preprocessing we use the Educe open source library (follow Installation Instructions for setup: https://educe.readthedocs.io/en/latest/rst-dt.html)
- RST Relation Classification Preprocessing.ipynb: preprocessing RST-DT to obtain EDU pairs with corresponding relations and relation classes
- run_classifier_rst.py - file to fine tune and evaluate BERT. Details on how to train the classifier are included below.
- RST Relation Classification Analysis.ipynb: analysis/plots for relation prediction 

To run relation classifer:
- create folder called relation_data and the csv files to it
- create folder called rst_model_base (the tuned model will be saved here)
- run:
python run_classifier_rst.py --data_dir relation_data/ --bert_model bert-base-uncased --task_name rst --output_dir rst_model_base --max_seq_length 384 --do_lower_case --do_train
- replace --do_train with --do_eval for testing
