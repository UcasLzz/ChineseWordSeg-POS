## 数据来源：2019百度信息抽取竞赛
百度网盘链接：链接：https://pan.baidu.com/s/1guSzi13XmHYrURFSi7I1wQ 
提取码：xeoi 


## NER Tagger

NER Tagger is an implementation of a Named Entity Recognizer that obtains state-of-the-art performance in NER on the 4 CoNLL datasets (English, Spanish, German and Dutch) without resorting to any language-specific knowledge or resources such as gazetteers. Details about the model can be found at: http://arxiv.org/abs/1603.01360


## Initial setup

To use the tagger, you need Python 2.7, with Numpy and Theano installed.


## Tag sentences

The fastest way to use the tagger is to use one of the pretrained models:

```
./tagger.py --model models/english/ --input input.txt --output output.txt
```

The input file should contain one sentence by line, and they have to be tokenized. Otherwise, the tagger will perform poorly.


## Train a model

To train your own model, you need to use the train.py script and provide the location of the training, development and testing set:

```
./train.py --train train.txt --dev dev.txt --test test.txt
```

The training script will automatically give a name to the model and store it in ./models/
There are many parameters you can tune (CRF, dropout rate, embedding dimension, LSTM hidden layer size, etc). To see all parameters, simply run:

```
./train.py --help
```

Input files for the training script have to follow the same format than the CoNLL2003 sharing task: each word has to be on a separate line, and there must be an empty line after each sentence. A line must contain at least 2 columns, the first one being the word itself, the last one being the named entity. It does not matter if there are extra columns that contain tags or chunks in between. Tags have to be given in the IOB format (it can be IOB1 or IOB2).


## Suggetsed Readings
Neural Architectures for Named Entity Recognition
https://aclweb.org/anthology/N16-1030

Bidirectional LSTM-CRF Models for Sequence Tagging
https://arxiv.org/pdf/1508.01991v1.pdf
