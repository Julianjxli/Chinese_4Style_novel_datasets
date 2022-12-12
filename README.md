# Chinese_4Style_novel_datasets
## overview  概要
Recent Chinese novel datasets are more often unsupervised datasets. And the chinese text classification dataset lacks a dataset for novel style classification. 
Even for novel texts with style labels, the labels are more for the whole novel. 
Such labels cannot accurately contain style information, because the information in a novel is messy. 
For example, in science fiction, there are also love stories between characters, and such a plot and text with the label "science fiction" will bring some confusion to the training.

Our original text data was obtained from Tencent AI Lab, which contains 25,184 novel categories. By fusing similar categories and cleaning, we selected 4 high quality categories as our target, which are science fiction, classical, military and officialdom. Among them, classical has stronger genre attributes, and after fusing other purely literary texts  from https://github.com/NiuTrans/Classical-Modern, we believe its feature boundary has been more clearly defined.

As for the others, we first extracted the top 50 keywords in the data of each novel style. The text extracted by keywords in the target style data is mixed with randomly extracted text from the non-target data to form 100,000 data texts for each style. Then we give these 100,000 pieces of data to professional annotators to annotate, and each piece of data is judged by them whether it is the target style or not.

Finally, our data includes not only the manual annotation results, but also the original target style data text in order to ensure the robustness of the data. The size of the number of the four styles of data and their distribution are shown in the Table\ref{datasets}. Our data are publicly available at https://drive.google.com/file/d/1wKDxO4lBRLlo1Zj7IM6fzZ77zJ5yJoRz/view?usp=share_link.





## Data Details 

### Cleaning steps
1. Clean up the novel according to its categories and remove the categories that do not fit. 
2. Remove the text under the introduction and inappropriate tag symbols in the novel.  
3. After the above finishing, the pornographic and dirty content is removed. 。


### Style data acquisition method 

1. Obtain a preliminary style dataset based on the fusion of tag information  
2. extract keywords in the preliminary style text dataset  
3. each style extracts target style sentences in the preliminary style dataset according to keywords, and forms a manually annotated dataset with a total of 100,000 sentences of non-target style  
4. professional annotator to annotate the data  
5. extracting strong style text (meaning that the frequency of style keywords is large) and weak style text (the frequency of style keywords is 0) from the preliminary style text to form a relevant dataset together with the annotated data.  


### The division of each style dataset

| Division | SF | CL | MI | PO |
|  ----  | ----  | ----  | ----  | ----  |
| training  | 138,389 | 285,330 | 186,895 | 174,502 |
| dev  | 5,000 | 5,000 | 5,000 | 5,000 |
| test  | 2,000 | 2,000 | 2,000 | 2,000 |
| proportion  | 45.49% | 51.28% | 52.78% | 54.90% |


