# E-Reviews

### 简介
广告文案生成，即给定关键的商品信息，生成合理的广告文案。该数据集由清华大学CoAI小组收集，用于数据到文本生成任务。

### 论文
[Long and Diverse Text Generation with Planning-based Hierarchical Variational Model](https://www.aclweb.org/anthology/D19-1321/). EMNLP 2019.

### 数据规模
训练集：114,599个广告文案，验证集：1,070个广告文案，测试集：3,127个广告文案。

### 数据格式描述
每条数据包含输入的商品信息(feature，以列表形式存储)和期待输出的广告文案(desc，以字符串形式存储)。

### 数据样例
```
{
	"feature":
		[["版型", "宽松"], ["风格", "休闲"], ["图案", "印花"], ["图案", "文字"], ["图案", "字母"], ["衣样式", "衫"], ["衣样式", "POLO"], ["衣领型", "翻领"]], 
	"desc": 
		"设计亮点broadcast这款宽松polo衫采用了个性翻领设计，显得十分的干练利索，带有主题字母印花，显得十分有个性，自然大方，休闲宽松版型，上身舒适。", 
}
```

- "feature" (`list of list`)：输入的商品信息。
- "desc" (`str`)：期待输出的广告文案。

### 评测代码
预测结果需要和评测代码保持一样的格式。
正确提交文件名：EReviews.jsonl

依赖：rouge\=\=1.0.0, jieba=0.42.1, nltk\=\=3.6.2, numpy\=\=1.20.3
```shell
python eval.py prediction_file test_private_file
```

评测指标为rouge-f, rouge-p, rouge-r，输出结果为字典格式：
```she
return {
    "rouge-f": _, 
    "rouge-p": _, 
    "rouge-r": _}
```

### 作者列表
邵智宏, 黄民烈，温江涛，徐文飞, 朱小燕

### 制作单位
清华大学

### 论文引用
```
@inproceedings{shao-etal-2019-long,
    title = "Long and Diverse Text Generation with Planning-based Hierarchical Variational Model",
    author = "Shao, Zhihong  and
      Huang, Minlie  and
      Wen, Jiangtao  and
      Xu, Wenfei  and
      Zhu, Xiaoyan",
    booktitle = "Proceedings of the 2019 Conference on Empirical Methods in Natural Language Processing and the 9th International Joint Conference on Natural Language Processing (EMNLP-IJCNLP)",
    year = "2019",
    pages = "3257--3268",
}
```
