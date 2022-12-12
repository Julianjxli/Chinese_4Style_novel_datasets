# Chinese_4Style_novel_datasets
## 概要
Recent Chinese novel datasets are more often unsupervised datasets. And the chinese text classification dataset lacks a dataset for novel style classification. 
Even for novel texts with style labels, the labels are more for the whole novel. 
Such labels cannot accurately contain style information, because the information in a novel is messy. 
For example, in science fiction, there are also love stories between characters, and such a plot and text with the label "science fiction" will bring some confusion to the training.

Our original text data was obtained from Tencent AI Lab, which contains 25,184 novel categories. By fusing similar categories and cleaning, we selected 4 high quality categories as our target, which are science fiction, classical, military and officialdom. Among them, classical has stronger genre attributes, and after fusing other purely literary texts  from https://github.com/NiuTrans/Classical-Modern, we believe its feature boundary has been more clearly defined.

As for the others, we first extracted the top 50 keywords in the data of each novel style. The text extracted by keywords in the target style data is mixed with randomly extracted text from the non-target data to form 100,000 data texts for each style. Then we give these 100,000 pieces of data to professional annotators to annotate, and each piece of data is judged by them whether it is the target style or not.

Finally, our data includes not only the manual annotation results, but also the original target style data text in order to ensure the robustness of the data. The size of the number of the four styles of data and their distribution are shown in the Table\ref{datasets}. Our data are publicly available at https://drive.google.com/file/d/1wKDxO4lBRLlo1Zj7IM6fzZ77zJ5yJoRz/view?usp=share_link.


最近的中文小说数据集更多的是无监督的数据集。而中文文本分类数据集缺乏用于小说风格分类的数据集。即使是带有风格标签的小说文本，其标签也多是针对整个小说的。这样的标签不能准确包含风格信息，因为小说中的信息是混乱的。例如，在科幻小说中，也有人物之间的爱情故事，这样的情节和带有 "科幻小说 "标签的文本会给训练带来一些混乱。

我们的原始文本数据来自腾讯AI Lab，其中包含25184个小说类别。通过融合相似类别和清洗，我们选择了4个高质量的类别作为我们的目标，它们是科幻、古典、军事和官方。其中，古典类具有较强的体裁属性，在融合了其他纯古典文学类文本后（https://github.com/NiuTrans/Classical-Modern），我们认为其特征边界已经比较明确。

至于其他的，我们首先提取了每种小说文体数据中的前50个关键词。将目标文体数据中按关键词提取的文本与非目标数据中随机提取的文本混合，形成每种文体的10万个数据文本。然后，我们将这10万条数据交给专业的注释人员进行注释，每条数据都由他们判断是否是目标文体。

最后，我们的数据不仅包括人工标注的结果，还包括原始的目标文体数据文本，以确保数据的稳健性。四种文体的数据数量大小及其分布见表ref{datasets}。我们的数据可以在以下网站公开获取 
https://drive.google.com/file/d/1wKDxO4lBRLlo1Zj7IM6fzZ77zJ5yJoRz/view?usp=share_link.


## 数据清洗

### 清理思路
1. 根据小说类别进行清理，去除不适合的类别。
2. 对小说中的介绍下文字以及不合适的标签符号进行去除
3. 经过上述整理后，对色情脏话内容进行删除

### 风格数据获取方法
1. 根据标签信息融合获取初步的风格数据集
2. 在初步的风格文本数据集中抽取关键词
3. 每个风格根据关键词在初步风格数据集中抽取目标风格句子，并与非目标风格的句子共计十万条组成人工标注的数据集
4. 专业标注人员对数据进行标注
5. 在初步风格文本中抽取强风格的文本（指风格关键词词频较大）和弱风格文本（风格关键词词频为0）与标注数据共同组成相关数据集。

### 风格数据集的划分

| Division | 科幻 | 古典 | 军事 | 官场 |
|  ----  | ----  | ----  | ----  | ----  |
| 训练集  | 138,389 | 285,330 | 186,895 | 174,502 |
| 验证集  | 5,000 | 5,000 | 5,000 | 5,000 |
| 测试集  | 2,000 | 2,000 | 2,000 | 2,000 |
| 正例占比  | 45.49% | 51.28% | 52.78% | 54.90% |
