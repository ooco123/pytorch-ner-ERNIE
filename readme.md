# ERNIE Pytorch ner 
p100-2 tmux attach -t zyy
# train
python3.5 run_bert_ner.py
ernie_weight
dataset:msra_ner&人民日报
https://cloud.tsinghua.edu.cn/d/b2017a770eac498999cf/
# Inference
confirm config.args.labels
python3.5 run_inference.py
input:data/inference.txt 
output:output/inference/inference.json
default weight load:output/checkpoint/pytorch_model.bin

# Result 
dataset：msra_ner
| with_crf_all_train | precision | recall | f1-score | support |
| ------------------ | --------- | ------ | -------- | ------- |
|                    |           |        |          |         |
| 0                  | 0.29      | 0.83   | 0.43     | 883     |
| 1                  | 0.9       | 0.99   | 0.94     | 1712    |
| 2                  | 0.92      | 0.77   | 0.84     | 983     |
| 3                  | 0.91      | 0.97   | 0.94     | 3939    |
| 4                  | 0.98      | 0.9    | 0.93     | 1832    |
| 5                  | 0.97      | 0.96   | 0.96     | 2434    |
| 6                  | 1         | 0.98   | 0.99     | 96440   |
|                    |           |        |          |         |
| micro avg          | 0.97      | 0.97   | 0.97     | 108223  |
| macro avg          | 0.85      | 0.91   | 0.86     | 108223  |
| weghted avg        | 0.98      | 0.97   | 0.98     | 108223  |


  | no_crf_all_train | precision | recall | f1-score | support |
| ---------------- | --------- | ------ | -------- | ------- |
|                  |           |        |          |         |
| 0                | 0         | 0      | 0        | 883     |
| 1                | 0.71      | 0.99   | 0.83     | 1712    |
| 2                | 0.85      | 0.96   | 0.9      | 983     |
| 3                | 0.95      | 0.97   | 0.96     | 3939    |
| 4                | 0.97      | 0.97   | 0.97     | 1832    |
| 5                | 0.97      | 0.96   | 0.96     | 2434    |
| 6                | 1         | 1      | 1        | 96440   |
|                  |           |        |          |         |
| micro avg        | 0.99      | 0.99   | 0.99     | 108223  |
| macro avg        | 0.78      | 0.84   | 0.8      | 108223  |
| weighted avg     | 0.98      | 0.99   | 0.98     | 108223  |

| with_crf_no_train_ernie | precision | recall | f1-score | support |
| ----------------------- | --------- | ------ | -------- | ------- |
|                         |           |        |          |         |
| 0                       | 0.24      | 0.68   | 0.36     | 883     |
| 1                       | 0.84      | 0.85   | 0.85     | 1712    |
| 2                       | 0.85      | 0.1    | 0.18     | 983     |
| 3                       | 0.75      | 0.33   | 0.46     | 3939    |
| 4                       | 0.74      | 0.68   | 0.71     | 1832    |
| 5                       | 0.78      | 0.62   | 0.69     | 2434    |
| 6                       | 0.96      | 0.98   | 0.97     | 96440   |
|                         |           |        |          |         |
| micro avg               | 0.93      | 0.93   | 0.93     | 108223  |
| macro avg               | 0.74      | 0.61   | 0.6      | 108223  |
| weighted avg            | 0.93      | 0.93   | 0.92     | 108223  |

| no_crf_no_train_ernie | precision | recall | f1-score | support |
| --------------------- | --------- | ------ | -------- | ------- |
|                       |           |        |          |         |
| 0                     | 0         | 0      | 0        | 883     |
| 1                     | 0.74      | 0.88   | 0.8      | 1712    |
| 2                     | 0.88      | 0.17   | 0.29     | 983     |
| 3                     | 0.82      | 0.36   | 0.5      | 3939    |
| 4                     | 0.73      | 0.77   | 0.75     | 1832    |
| 5                     | 0.79      | 0.64   | 0.7      | 2434    |
| 6                     | 0.96      | 1      | 0.98     | 96440   |
|                       |           |        |          |         |
| micro avg             | 0.94      | 0.94   | 0.94     | 108223  |
| macro avg             | 0.7       | 0.54   | 0.57     | 108223  |
| weighted avg          | 0.93      | 0.94   | 0.93     | 108223  |



