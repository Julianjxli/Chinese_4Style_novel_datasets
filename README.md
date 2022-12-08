# Chinese_4Style_novel_datasets
Recent Chinese novel datasets are more often unsupervised datasets. And the chinese text classification dataset lacks a dataset for novel style classification. 
Even for novel texts with style labels, the labels are more for the whole novel. 
Such labels cannot accurately contain style information, because the information in a novel is messy. 
For example, in science fiction, there are also love stories between characters, and such a plot and text with the label "science fiction" will bring some confusion to the training.

Our original text data was obtained from Tencent AI Lab, which contains 25,184 novel categories. By fusing similar categories and cleaning, we selected 4 high quality categories as our target, which are science fiction, classical, military and officialdom. Among them, classical has stronger genre attributes, and after fusing other purely literary texts\footnote{https://github.com/NiuTrans/Classical-Modern}, we believe its feature boundary has been more clearly defined.

As for the others, we first extracted the top 50 keywords in the data of each novel style. The text extracted by keywords in the target style data is mixed with randomly extracted text from the non-target data to form 100,000 data texts for each style. Then we give these 100,000 pieces of data to professional annotators to annotate, and each piece of data is judged by them whether it is the target style or not.

Finally, our data includes not only the manual annotation results, but also the original target style data text in order to ensure the robustness of the data. The size of the number of the four styles of data and their distribution are shown in the Table\ref{datasets}. Our data are publicly available at.
