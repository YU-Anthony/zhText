# E-Reviews

### Introduction
Advertising text generation refers to the generation of reasonable advertising text given some key product information. This dataset was collected by the CoAI team of Tsinghua University for the data-to-text generation task.

### Paper
[Long and Diverse Text Generation with Planning-based Hierarchical Variational Model](https://www.aclweb.org/anthology/D19-1321/). EMNLP 2019.

### Data Size
Training set: 114,599; Validation set: 1,070; Test set: 3,127.

### Data Format
Each instance is composed of input product information (feature, a list) and expected Advertising text (desc, a string). 

### Example
```
{
	"feature":
		[["版型", "宽松"], ["风格", "休闲"], ["图案", "印花"], ["图案", "文字"], ["图案", "字母"], ["衣样式", "衫"], ["衣样式", "POLO"], ["衣领型", "翻领"]], 
	"desc": 
		"设计亮点broadcast这款宽松polo衫采用了个性翻领设计，显得十分的干练利索，带有主题字母印花，显得十分有个性，自然大方，休闲宽松版型，上身舒适。", 
}
```

- "features" (`list of list`): input product information.
- "desc" (`str`): expected Advertising text.

### Evaluation Code
The prediction result is consistent with the format of the evaluation code.
The correct file name is EReviews.jsonl.

Dependency packages: rouge\=\=1.0.0, jieba=0.42.1, nltk\=\=3.6.2, numpy\=\=1.20.3
```shell
python eval.py prediction_file test_private_file
```

The evaluation metrics are rouge-f, rouge-p, rouge-r, and the output is in dictionary format.
```she
return {
    "rouge-f": _, 
    "rouge-p": _, 
    "rouge-r": _}
```

### Author List
Zhihong Shao, Minlie Huang, Jiangtao Wen, Wenfei Xu, Xiaoyan Zhu

### Institutions
Tsinghua University

### Citation
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
