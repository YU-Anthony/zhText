## 数据格式

OCNLI，即原生中文自然语言推理数据集，是第一个非翻译的、使用原生汉语的大型中文自然语言推理数据集。

数据量：train: 50k， dev(3k), test(3k) 

所有数据均为 json 格式:

```
{
"level":"medium",
"sentence1":"身上裹一件工厂发的棉大衣,手插在袖筒里",
"sentence2":"身上至少一件衣服",
"label":"entailment","label0":"entailment","label1":"entailment","label2":"entailment","label3":"entailment","label4":"entailment",
"genre":"lit","prem_id":"lit_635","id":0
}
```

where:

- `level`: `easy`, `medium` and `hard` refer to the 1st, 2nd and 3rd hypothesis the annotator wrote respectively for that premise and label. See our paper for details. 【难度】: `easy`, `medium`, `hard`分别代表标注人员为某一标签（如entailment）写的第一、第二、第三个假设。我们预计三者难度递增。具体数据收集方式请参考论文。
- `sentence1`: the premise sentence(s) 【句子1】，即前提。
- `sentence2`: the hypothesis sentence(s) 【句子2】，即假设。
- `label`: majority vote from label0 -- label4. If no majority agreement, the label will be `-`, and this example should be excluded in experiments, same as in SNLI and MNLI (already taken care of in our baseline code) 【标签】，即标签0 -- 标签4的majority vote。如果标签为'-'，则此数据应除去，因为5名标注人员没有得出共识，此项设置与SNLI/MNLI相同。
- `label0` -- `label4`: 5 annotated labels for the NLI pair. All pairs in dev and test have 5 labels, whereas only a small portion in the training set has 5 labels 【5个标签】，验证集与测试集的数据均有5个标签。训练集仅部分数据有5个标签。
- `genre`: one of `gov`, `news`, `lit`, `tv` and `phone` 【文本类别】，共5类：政府公报、新闻、文学、电视谈话节目、电话转写。
- `prem_id`: id for the premise 【前提编号】
- `id`: overall id 【总编号】

训练和验证时仅需【sentence1】【sentence2】【label】

## 
