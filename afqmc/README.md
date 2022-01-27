# AFQMC 蚂蚁金融语义相似度 Ant Financial Question Matching Corpus

数据量：训练集（34334）验证集（4316）测试集（3861）

例子：

{"sentence1": "双十一花呗提额在哪", "sentence2": "里可以提花呗额度", "label": "0"}

每一条数据有三个属性，从前往后分别是 句子1，句子2，句子相似度标签。其中label标签，1 表示sentence1和sentence2的含义类似，0表示两个句子的含义不同。
