# CSC2511 Course Project

**File Descriptions:**

Task 1: Next EDU Prediction
- 1 Next EDU Preprocessing.ipynb: preprocessing RST-DT to generate adjacent EDU pairs
- 2 Next EDU Prediction.ipynb: runs BertForNextSentencePrediction Model
- 3 Next EDU Prediction Analysis.ipynb: analysis/plots for next EDU prediction

Task 2: RST Relation Classification
- < > preprocessing RST-DT to obtain EDU pair - relation 
- run_classifier_rst.py - file to fine tune and evaluate BERT. Details on how to train the classifier are included below.
- RST Relation Classification Analysis.ipynb: analysis/plots for relation prediction 

To run relation classifer:
- create folder called relation_data and the csv files to it
- create folder called rst_model_base (the tuned model will be saved here)
- run:
python run_classifier_rst.py --data_dir relation_data/ --bert_model bert-base-uncased --task_name rst --output_dir rst_model_base --max_seq_length 384 --do_lower_case --do_train
- replace --do_train with --do_eval for testing
