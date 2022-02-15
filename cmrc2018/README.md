# CMRC2018

CMRC 是一个由人类专家注释的数据集，包含近20，000个问题。初始数据集来源于维基百科网页的dump2的中文部分，通过开源工具Wikipedia Extractor3 将原始文件预处理为纯文本,并使用opencc4工具包将繁体字转换为简体字，以达到规范化的目的。



该数据集源自于 [CLUE benchmark](https://github.com/CLUEbenchmark/CLUE), 愿数据集中共有 train.json, eval.json, test.json, trial.json 四个文件。根据[官网](https://hfl-rc.com/cmrc2018/task/)介绍 试验集可加入到训练集中用来扩充训练数据，故该仓库中 train.json 文件其实是 clue 仓库中 train.json 和 trial.json 的合集。

