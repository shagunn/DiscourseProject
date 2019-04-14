# DiscourseProject


To run relation classifer:
- create folder called relation_data and the csv files to it
- create folder called rst_model_base (the tuned model will be saved here)
- run:
python run_classifier_rst.py --data_dir relation_data/ --bert_model bert-base-uncased --task_name rst --output_dir rst_model_base --max_seq_length 384 --do_lower_case --do_train
