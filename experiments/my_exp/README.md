This folder contains examples to show how to make your own task.

## [RACE](http://www.qizhexie.com/data/RACE_leaderboard.html)
The RACE dataset is a large-scale ReAding Comprehension dataset collected from English Examinations that are created for middle school and high school students.

To get start you need to download data from http://www.cs.cmu.edu/~glai1/data/race/, then run `run_race.sh`.

```
cd experiments/my_exp

CUDA_VISIBLE_DEVICES=1 python -m DeBERTa.apps.run --model_config config.json  \
        --tag base-mnli \
        --do_train \
        --task_dir . \
        --task_name MyRACE \
        --data_dir race \
        --init_model base-mnli \
        --output_dir output/train --num_train_epochs 6 \
        --warmup 100 \
        --learning_rate 2e-5 \
        --train_batch_size 32 \
        --cls_drop_out 0.2 \
        --max_seq_len 320

```


## [AlphaNLI](https://leaderboard.allenai.org/anli/submissions/public)
Abductive Natural Language Inference (aNLI) is a new commonsense benchmark dataset designed to test an AI system’s capability to apply abductive reasoning and common sense to form possible explanations for a given set of observations. Formulated as a binary-classification task, the goal is to pick the most plausible explanatory hypothesis given two observations from narrative contexts.

To get start you need to download data from https://leaderboard.allenai.org/anli/submissions/public, then run `run_anli.sh`.
