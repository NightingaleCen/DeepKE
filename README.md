<p align="center">
    <a href="https://github.com/zjunlp/deepke"> <img src="pics/logo.png" width="400"/></a>
<p>
<p align="center">  
    <a href="http://deepke.zjukg.cn">
        <img alt="Documentation" src="https://img.shields.io/badge/demo-website-blue">
    </a>
    <a href="https://pypi.org/project/deepke/#files">
        <img alt="PyPI" src="https://img.shields.io/pypi/v/deepke">
    </a>
    <a href="https://github.com/zjunlp/DeepKE/blob/master/LICENSE">
        <img alt="GitHub" src="https://img.shields.io/github/license/zjunlp/deepke">
    </a>
    <a href="http://zjunlp.github.io/DeepKE">
        <img alt="Documentation" src="https://img.shields.io/badge/doc-website-red">
    </a>
    <a href="https://colab.research.google.com/drive/1vS8YJhJltzw3hpJczPt24O0Azcs3ZpRi?usp=sharing">
        <img alt="Open In Colab" src="https://colab.research.google.com/assets/colab-badge.svg">
    </a>
</p>


<p align="center">
    <b> English | <a href="https://github.com/zjunlp/DeepKE/blob/main/README_CN.md">简体中文</a> </b>
</p>

<h1 align="center">
    <p>A Deep Learning Based Knowledge Extraction Toolkit<br>for Knowledge Graph Construction</p>
</h1>


[DeepKE](https://arxiv.org/pdf/2201.03335.pdf) is a knowledge extraction toolkit for knowledge graph construction supporting **cnSchema**，**low-resource**, **document-level** and **multimodal** scenarios for *entity*, *relation* and *attribute* extraction. We provide [documents](https://zjunlp.github.io/DeepKE/), [Google Colab tutorials](https://colab.research.google.com/drive/1vS8YJhJltzw3hpJczPt24O0Azcs3ZpRi?usp=sharing), [online demo](http://deepke.zjukg.cn/), [paper](https://arxiv.org/pdf/2201.03335.pdf), [slides](https://drive.google.com/file/d/1IIeIZAbVduemqXc4zD40FUMoPHCJinLy/view?usp=sharing) and [poster](https://drive.google.com/file/d/1vd7xVHlWzoAxivN4T5qKrcqIGDcSM1_7/view?usp=sharing) for beginners.

**Reading Materials**:

Data-Efficient Knowledge Graph Construction, 高效知识图谱构建 ([Tutorial on CCKS 2022](http://sigkg.cn/ccks2022/?page_id=24)) \[[slides](https://drive.google.com/drive/folders/1xqeREw3dSiw-Y1rxLDx77r0hGUvHnuuE)\] 

Efficient and Robust Knowledge Graph Construction ([Tutorial on AACL-IJCNLP 2022](https://www.aacl2022.org/Program/tutorials)) \[[slides](https://github.com/NLP-Tutorials/AACL-IJCNLP2022-KGC-Tutorial)\] 

PromptKG Family: a Gallery of Prompt Learning & KG-related Research Works, Toolkits, and Paper-list [[Resources](https://github.com/zjunlp/PromptKG)\] 

Knowledge Extraction in Low-Resource Scenarios: Survey and Perspective \[[Survey](https://arxiv.org/abs/2202.08063)\]\[[Paper-list](https://github.com/zjunlp/Low-resource-KEPapers)\]

Reasoning with Language Model Prompting \[[Survey](https://arxiv.org/abs/2212.09597)\]\[[Paper-list](https://github.com/zjunlp/Prompt4ReasoningPapers)\]

**Related Toolkit**:

[Doccano](https://github.com/doccano/doccano)、[MarkTool](https://github.com/FXLP/MarkTool)、[LabelStudio](https://labelstud.io/ ): Data Annotation Toolkits

[LambdaKG](https://github.com/zjunlp/PromptKG/tree/main/lambdaKG): A library and benchmark for PLM-based KG embeddings

# Table of Contents

* [What's New](#whats-new)
* [Prediction Demo](#prediction-demo)
* [Model Framework](#model-framework)
* [Quick Start](#quick-start)
   * [Requirements](#requirements)
   * [Introduction of Three Functions](#introduction-of-three-functions)
      * [1. Named Entity Recognition](#1-named-entity-recognition)
      * [2. Relation Extraction](#2-relation-extraction)
      * [3. Attribute Extraction](#3-attribute-extraction)
* [Notebook Tutorial](#notebook-tutorial)
* [Tips](#tips)
* [To do](#to-do)
* [Citation](#citation)
* [Contributors](#contributors)
* [Other Knowledge Extraction Open-Source Projects](#other-knowledge-extraction-open-source-projects)

<br>

# What's New
## Feb, 2023
* We have supported using [LLM](https://github.com/zjunlp/DeepKE/tree/main/example/llm) (GPT-3) with in-context learning (based on [Promptify](https://github.com/promptslab/Promptify)) & data generation, added a NER model [W2NER](https://github.com/zjunlp/DeepKE/tree/main/example/ner/standard/w2ner).
## Nov, 2022
* Add data [annotation instructions](https://github.com/zjunlp/DeepKE/blob/main/README_TAG.md) for entity recognition and relation extraction, automatic labelling of weakly supervised data ([entity extraction](https://github.com/zjunlp/DeepKE/tree/main/example/ner/prepare-data) and [relation extraction](https://github.com/zjunlp/DeepKE/tree/main/example/re/prepare-data)), and optimize [multi-GPU training](https://github.com/zjunlp/DeepKE/tree/main/example/re/standard).
## Sept, 2022
* The paper [DeepKE: A Deep Learning Based Knowledge Extraction Toolkit for Knowledge Base Population](https://arxiv.org/abs/2201.03335) has been accepted by the EMNLP 2022 System Demonstration Track.
## Aug, 2022
* We have added [data augmentation](https://github.com/zjunlp/DeepKE/tree/main/example/re/few-shot/DA) (Chinese, English) support for [low-resource relation extraction](https://github.com/zjunlp/DeepKE/tree/main/example/re/few-shot).
## June, 2022
* We have added multimodal support for [entity](https://github.com/zjunlp/DeepKE/tree/main/example/ner/multimodal) and [relation extraction](https://github.com/zjunlp/DeepKE/tree/main/example/re/multimodal).
## May, 2022
* We have released [DeepKE-cnschema](https://github.com/zjunlp/DeepKE/blob/main/README_CNSCHEMA.md) with off-the-shelf knowledge extraction models.
## Jan, 2022
* We have released a paper [DeepKE: A Deep Learning Based Knowledge Extraction Toolkit for Knowledge Base Population](https://arxiv.org/abs/2201.03335)
## Dec, 2021
* We have added `dockerfile` to create the enviroment automatically. 
## Nov, 2021
* The demo of DeepKE, supporting real-time extration without deploying and training, has been released.
* The documentation of DeepKE, containing the details of DeepKE such as source codes and datasets, has been released.
## Oct, 2021
* `pip install deepke`
* The codes of deepke-v2.0 have been released.
## Aug, 2019
* The codes of deepke-v1.0 have been released.
## Aug, 2018
* The project DeepKE startup and codes of deepke-v0.1 have been released.
<br>

# Prediction Demo

There is a demonstration of prediction. The GIF file is created by [Terminalizer](https://github.com/faressoft/terminalizer). Get the [code](https://drive.google.com/file/d/1r4tWfAkpvynH3CBSgd-XG79rf-pB-KR3/view?usp=share_link).
<img src="pics/demo.gif" width="636" height="494" align=center>

<br>

# Model Framework

<h3 align="center">
    <img src="pics/architectures.png">
</h3>


- DeepKE contains a unified framework for **named entity recognition**, **relation extraction** and **attribute extraction**, the three  knowledge extraction functions.
- Each task can be implemented in different scenarios. For example, we can achieve relation extraction in **standard**, **low-resource (few-shot)**, **document-level** and **multimodal** settings.
- Each application scenario comprises of three components: **Data** including Tokenizer, Preprocessor and Loader, **Model** including Module, Encoder and Forwarder, **Core** including Training, Evaluation and Prediction. 

<br>

# Quick Start

*DeepKE* supports `pip install deepke`. <br>Take the fully supervised relation extraction for example.

**Step1** Download the basic code

```bash
git clone --depth 1 https://github.com/zjunlp/DeepKE.git
```

**Step2** Create a virtual environment using `Anaconda` and enter it.<br>

 - **❗NOTE: We provide a [Dockerfile](https://github.com/zjunlp/DeepKE/tree/main/docker) with [tutorials](https://github.com/zjunlp/DeepKE/issues/145) please refer to the [Tips](#tips) to speed up installation**

```bash
conda create -n deepke python=3.8

conda activate deepke
```

1. Install *DeepKE* with source code (**Recommended**)

   ```bash
   python setup.py install
   
   python setup.py develop
   ```

2. Install *DeepKE* with `pip`

   ```bash
   pip install deepke
   ```
   

**Step3** Enter the task directory

```bash
cd DeepKE/example/re/standard
```

**Step4** Download the dataset, or follow the [annotation instructions](https://github.com/zjunlp/DeepKE/blob/main/README_TAG.md) to obtain data

```bash
wget 120.27.214.45/Data/re/standard/data.tar.gz

tar -xzvf data.tar.gz
```

Many types of data formats are supported,and details are in each part. 

**Step5** Training (Parameters for training can be changed in the `conf` folder)

We support visual parameter tuning by using *[wandb](https://docs.wandb.ai/quickstart)*.

```bash
python run.py
```

**Step6** Prediction (Parameters for prediction can be changed in the `conf` folder)

Modify the path of the trained model in `predict.yaml`.The absolute path of the model needs to be used，such as `xxx/checkpoints/2019-12-03_ 17-35-30/cnn_ epoch21.pth`.

```bash
python predict.py
```

 - **❗NOTE: if you encounter any errors, please refer to the [Tips](#tips) or submit a GitHub issue.**

## Requirements

> python == 3.8

- torch == 1.5
- hydra-core == 1.0.6
- tensorboard == 2.4.1
- matplotlib == 3.4.1
- transformers == 3.4.0
- jieba == 0.42.1
- scikit-learn == 0.24.1
- pytorch-transformers == 1.2.0
- seqeval == 1.2.2
- tqdm == 4.60.0
- opt-einsum==3.3.0
- wandb==0.12.7
- ujson

## Introduction of Three Functions

### 1. Named Entity Recognition

- Named entity recognition seeks to locate and classify named entities mentioned in unstructured text into pre-defined categories such as person names, organizations, locations, organizations, etc.

- The data is stored in `.txt` files. Some instances as following (Users can label data based on the tools [Doccano](https://github.com/doccano/doccano), [MarkTool](https://github.com/FXLP/MarkTool), or they can use the [Weak Supervision](https://github.com/zjunlp/DeepKE/blob/main/example/ner/prepare-data) with DeepKE to obtain data automatically):

  |                           Sentence                           |           Person           |    Location    |          Organization          |
  | :----------------------------------------------------------: | :------------------------: | :------------: | :----------------------------: |
  | 本报北京9月4日讯记者杨涌报道：部分省区人民日报宣传发行工作座谈会9月3日在4日在京举行。 |            杨涌            |      北京      |            人民日报            |
  | 《红楼梦》由王扶林导演，周汝昌、王蒙、周岭等多位专家参与制作。 | 王扶林，周汝昌，王蒙，周岭 |            |  |
  | 秦始皇兵马俑位于陕西省西安市,是世界八大奇迹之一。 |           秦始皇           | 陕西省，西安市 |                          |

- Read the detailed process in specific README
  - **[STANDARD (Fully Supervised)](https://github.com/zjunlp/DeepKE/tree/main/example/ner/standard)**
    
    ***We [support LLM](https://github.com/zjunlp/DeepKE/tree/main/example/llm) and provide the off-the-shelf model, [DeepKE-cnSchema-NER](https://github.com/zjunlp/DeepKE/blob/main/README_CNSCHEMA_CN.md), which will extract entities in cnSchema without training.***

    **Step1** Enter  `DeepKE/example/ner/standard`.  Download the dataset.

    ```bash
    wget 120.27.214.45/Data/ner/standard/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```

    **Step2** Training<br>

    The dataset and parameters can be customized in the `data` folder and `conf` folder respectively.
  
    ```bash
    python run.py
    ```

    **Step3** Prediction

    ```bash
    python predict.py
    ```
  
  - **[FEW-SHOT](https://github.com/zjunlp/DeepKE/tree/main/example/ner/few-shot)**

    **Step1** Enter  `DeepKE/example/ner/few-shot`.  Download the dataset.

    ```bash
    wget 120.27.214.45/Data/ner/few_shot/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```
  
    **Step2** Training in the low-resouce setting <br>
  
    The directory where the model is loaded and saved and the configuration parameters can be cusomized in the `conf` folder.
  
    ```bash
    python run.py +train=few_shot
    ```
    
    Users can modify `load_path` in `conf/train/few_shot.yaml` to use existing loaded model.<br>
    
    **Step3** Add `- predict` to `conf/config.yaml`, modify `loda_path` as the model path and `write_path` as the path where the predicted results are saved in `conf/predict.yaml`, and then run `python predict.py`
    
    ```bash
    python predict.py
    ```

  - **[MULTIMODAL](https://github.com/zjunlp/DeepKE/tree/main/example/ner/multimodal)**

    **Step1** Enter  `DeepKE/example/ner/multimodal`.  Download the dataset.

    ```bash
    wget 120.27.214.45/Data/ner/multimodal/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```

    We use RCNN detected objects and visual grounding objects from original images as visual local information, where RCNN via [faster_rcnn](https://github.com/pytorch/vision/blob/main/torchvision/models/detection/faster_rcnn.py) and visual grounding via [onestage_grounding](https://github.com/zyang-ur/onestage_grounding).

    **Step2** Training in the multimodal setting <br>

    - The dataset and parameters can be customized in the `data` folder and `conf` folder respectively.
    - Start with the model trained last time: modify `load_path` in `conf/train.yaml`as the path where the model trained last time was saved. And the path saving logs generated in training can be customized by `log_dir`.

    ```bash
    python run.py
    ```

    **Step3** Prediction

    ```bash
    python predict.py
    ```

### 2. Relation Extraction

- Relationship extraction is the task of extracting semantic relations between entities from a unstructured text.

- The data is stored in `.csv` files. Some instances as following (Users can label data based on the tools [Doccano](https://github.com/doccano/doccano), [MarkTool](https://github.com/FXLP/MarkTool), or they can use the [Weak Supervision](https://github.com/zjunlp/DeepKE/blob/main/example/re/prepare-data) with DeepKE to obtain data automatically):

  |                        Sentence                        | Relation |    Head    | Head_offset |    Tail    | Tail_offset |
  | :----------------------------------------------------: | :------: | :--------: | :---------: | :--------: | :---------: |
  | 《岳父也是爹》是王军执导的电视剧，由马恩然、范明主演。 |   导演   | 岳父也是爹 |      1      |    王军    |      8      |
  |  《九玄珠》是在纵横中文网连载的一部小说，作者是龙马。  | 连载网站 |   九玄珠   |      1      | 纵横中文网 |      7      |
  |     提起杭州的美景，西湖总是第一个映入脑海的词语。     | 所在城市 |    西湖    |      8      |    杭州    |      2      |

- **!NOTE: If there are multiple entity types for one relation, entity types can be prefixed with the relation as inputs.**
- Read the detailed process in specific README

  - **[STANDARD (Fully Supervised)](https://github.com/zjunlp/DeepKE/tree/main/example/re/standard)** 

    ***We [support LLM](https://github.com/zjunlp/DeepKE/tree/main/example/llm) and provide the off-the-shelf model, [DeepKE-cnSchema-RE](https://github.com/zjunlp/DeepKE/blob/main/README_CNSCHEMA_CN.md), which will extract relations in cnSchema without training.***

    **Step1** Enter the `DeepKE/example/re/standard` folder.  Download the dataset.

    ```bash
    wget 120.27.214.45/Data/re/standard/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```

    **Step2** Training<br>

    The dataset and parameters can be customized in the `data` folder and `conf` folder respectively.
  
    ```bash
    python run.py
    ```

    **Step3** Prediction

    ```bash
    python predict.py
    ```
  
  - **[FEW-SHOT](https://github.com/zjunlp/DeepKE/tree/main/example/re/few-shot)**

    **Step1** Enter `DeepKE/example/re/few-shot`. Download the dataset.

    ```bash
    wget 120.27.214.45/Data/re/few_shot/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```

    **Step 2** Training<br>

    - The dataset and parameters can be customized in the `data` folder and `conf` folder respectively.
    - Start with the model trained last time: modify `train_from_saved_model` in `conf/train.yaml`as the path where the model trained last time was saved. And the path saving logs generated in training can be customized by `log_dir`. 
  
    ```bash
    python run.py
    ```
  
    **Step3** Prediction
  
    ```bash
    python predict.py
    ```
  
  - **[DOCUMENT](https://github.com/zjunlp/DeepKE/tree/main/example/re/document)**<br>
  
    **Step1** Enter `DeepKE/example/re/document`.  Download the dataset.
  
    ```bash
    wget 120.27.214.45/Data/re/document/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```
    
    **Step2** Training<br>
  
    - The dataset and parameters can be customized in the `data` folder and `conf` folder respectively.
    - Start with the model trained last time: modify `train_from_saved_model` in `conf/train.yaml`as the path where the model trained last time was saved. And the path saving logs generated in training can be customized by `log_dir`. 
    
    ```bash
    python run.py
    ```
    
    **Step3** Prediction
    
    ```bash
    python predict.py
    ```

  - **[MULTIMODAL](https://github.com/zjunlp/DeepKE/tree/main/example/re/multimodal)**

    **Step1** Enter  `DeepKE/example/re/multimodal`.  Download the dataset.

    ```bash
    wget 120.27.214.45/Data/re/multimodal/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```

    We use RCNN detected objects and visual grounding objects from original images as visual local information, where RCNN via [faster_rcnn](https://github.com/pytorch/vision/blob/main/torchvision/models/detection/faster_rcnn.py) and visual grounding via [onestage_grounding](https://github.com/zyang-ur/onestage_grounding).

    **Step2** Training<br>

    - The dataset and parameters can be customized in the `data` folder and `conf` folder respectively.
    - Start with the model trained last time: modify `load_path` in `conf/train.yaml`as the path where the model trained last time was saved. And the path saving logs generated in training can be customized by `log_dir`.

    ```bash
    python run.py
    ```

    **Step3** Prediction

    ```bash
    python predict.py
    ```

### 3. Attribute Extraction

- Attribute extraction is to extract attributes for entities in a unstructed text.

- The data is stored in `.csv` files. Some instances as following:

  |                           Sentence                           |   Att    |   Ent    | Ent_offset |      Val      | Val_offset |
  | :----------------------------------------------------------: | :------: | :------: | :--------: | :-----------: | :--------: |
  |          张冬梅，女，汉族，1968年2月生，河南淇县人           |   民族   |  张冬梅  |     0      |     汉族      |     6      |
  |诸葛亮，字孔明，三国时期杰出的军事家、文学家、发明家。|   朝代   |   诸葛亮   |     0      |     三国时期      |     8     |
  |        2014年10月1日许鞍华执导的电影《黄金时代》上映         | 上映时间 | 黄金时代 |     19     | 2014年10月1日 |     0      |

- Read the detailed process in specific README
  - **[STANDARD (Fully Supervised)](https://github.com/zjunlp/DeepKE/tree/main/example/ae/standard)**

    **Step1** Enter the `DeepKE/example/ae/standard` folder. Download the dataset.

    ```bash
    wget 120.27.214.45/Data/ae/standard/data.tar.gz
    
    tar -xzvf data.tar.gz
    ```

    **Step2** Training<br>

    The dataset and parameters can be customized in the `data` folder and `conf` folder respectively.
    
    ```bash
    python run.py
    ```
    
    **Step3** Prediction
    
    ```bash
    python predict.py
    ```

<br>

# Notebook Tutorial

This toolkit provides many `Jupyter Notebook` and `Google Colab` tutorials. Users can study *DeepKE* with them.

- Standard Setting<br>

  [NER Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/ner/standard/standard_ner_tutorial.ipynb)

  [NER Colab](https://colab.research.google.com/drive/1h4k6-_oNEHBRxrnzpxHPczO5SFaLS9uq?usp=sharing)

  [RE Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/re/standard/standard_re_pcnn_tutorial.ipynb)

  [RE Colab](https://colab.research.google.com/drive/1o6rKIxBqrGZNnA2IMXqiSsY2GWANAZLl?usp=sharing)

  [AE Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/ae/standard/standard_ae_tutorial.ipynb)

  [AE Colab](https://colab.research.google.com/drive/1pgPouEtHMR7L9Z-QfG1sPYkJfrtRt8ML)

- Low-resource<br>

  [NER Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/ner/few-shot/fewshot_ner_tutorial.ipynb)

  [NER Colab](https://colab.research.google.com/drive/1Xz0sNpYQNbkjhebCG5djrwM8Mj2Crj7F?usp=sharing)

  [RE Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/re/few-shot/fewshot_re_tutorial.ipynb)
  
  [RE Colab](https://colab.research.google.com/drive/1o1ly6ORgerkm1fCDjEQb7hsN5WKyg3JH?usp=sharing)


- Document-level<br>

  [RE Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/re/document/document_re_tutorial.ipynb)

  [RE Colab](https://colab.research.google.com/drive/1RGUBbbOBHlWJ1NXQLtP_YEUktntHtROa?usp=sharing)

- Multimodal<br>

  [NER Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/ner/multimodal/multimodal_ner_tutorial.ipynb)

  [NER Colab](https://colab.research.google.com/drive/1zOVZcn2v6xfCq39N80lbbHTdAfc7eGHb?usp=sharing)

  [RE Notebook](https://github.com/zjunlp/DeepKE/blob/main/tutorial-notebooks/re/multimodal/multimodal_re_tutorial.ipynb)

  [RE Colab](https://colab.research.google.com/drive/1ZRqqXMSDWoPpAKL7h9w9pq-SY-2gjc-u?usp=sharing)
  

<br>

# Tips

1.```Using nearest mirror```, **[THU](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/) in China, will speed up the installation of *Anaconda*; [aliyun](http://mirrors.aliyun.com/pypi/simple/) in China, will speed up `pip install XXX`**.

2.When encountering `ModuleNotFoundError: No module named 'past'`，run `pip install future` .

3.It's slow to install the pretrained language models online. Recommend download pretrained models before use and save them in the `pretrained` folder. Read `README.md` in every task directory to check the specific requirement for saving pretrained models.

4.The old version of *DeepKE* is in the [deepke-v1.0](https://github.com/zjunlp/DeepKE/tree/deepke-v1.0) branch. Users can change the branch to use the old version. The old version has been totally transfered to the standard relation extraction ([example/re/standard](https://github.com/zjunlp/DeepKE/blob/main/example/re/standard/README.md)).

5.It's recommended to install *DeepKE* with source codes. Because user may meet some problems in Windows system with 'pip',and the source code modification will not work,see[issue](https://github.com/zjunlp/DeepKE/issues/117)

6.More related low-resource knowledge extraction  works can be found in [Knowledge Extraction in Low-Resource Scenarios: Survey and Perspective](https://arxiv.org/pdf/2202.08063.pdf).

7.Make sure the exact versions of requirements in `requirements.txt`.



<br>

# To do
In next version, we plan to add **event extraction** to the toolkit. 

Meanwhile, we will offer long-term maintenance to **fix bugs**, **solve issues** and meet **new requests**. So if you have any problems, please put issues to us.

<br>

# Citation

Please cite our paper if you use DeepKE in your work

```bibtex
@inproceedings{zhang-etal-2022-deepke,
    title = "{D}eep{KE}: A Deep Learning Based Knowledge Extraction Toolkit for Knowledge Base Population",
    author = "Zhang, Ningyu  and
      Xu, Xin  and
      Tao, Liankuan  and
      Yu, Haiyang  and
      Ye, Hongbin  and
      Qiao, Shuofei  and
      Xie, Xin  and
      Chen, Xiang  and
      Li, Zhoubo  and
      Li, Lei",
    booktitle = "Proceedings of the The 2022 Conference on Empirical Methods in Natural Language Processing: System Demonstrations",
    month = dec,
    year = "2022",
    address = "Abu Dhabi, UAE",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2022.emnlp-demos.10",
    pages = "98--108",
    abstract = "We present an open-source and extensible knowledge extraction toolkit DeepKE, supporting complicated low-resource, document-level and multimodal scenarios in the knowledge base population. DeepKE implements various information extraction tasks, including named entity recognition, relation extraction and attribute extraction. With a unified framework, DeepKE allows developers and researchers to customize datasets and models to extract information from unstructured data according to their requirements. Specifically, DeepKE not only provides various functional modules and model implementation for different tasks and scenarios but also organizes all components by consistent frameworks to maintain sufficient modularity and extensibility. We release the source code at GitHub in https://github.com/zjunlp/DeepKE with Google Colab tutorials and comprehensive documents for beginners. Besides, we present an online system in http://deepke.openkg.cn/EN/re{\_}doc{\_}show.html for real-time extraction of various tasks, and a demo video.",
}
```
<br>

# Contributors

Zhejiang University: [Ningyu Zhang](https://person.zju.edu.cn/en/ningyu), Liankuan Tao, Xin Xu, Xinrong Li, Haiyang Yu, Hongbin Ye, Shuofei Qiao, Peng Wang, Yuqi Zhu, Xin Xie, Xiang Chen, Zhoubo Li, Lei Li, Xiaozhuan Liang, Yunzhi Yao, Shumin Deng, Wen Zhang, Guozhou Zheng, Huajun Chen

Community Contributors: [thredreams](https://github.com/thredreams), [eltociear](https://github.com/eltociear)

Alibaba Group: Feiyu Xiong, Qiang Chen

DAMO Academy: Zhenru Zhang, Chuanqi Tan, Fei Huang

# Other Knowledge Extraction Open-Source Projects

- [CogIE](https://github.com/jinzhuoran/CogIE)
- [OpenNRE](https://github.com/thunlp/OpenNRE)
- [OmniEvent](https://github.com/THU-KEG/OmniEvent)
- [OpenUE](https://github.com/zjunlp/OpenUE)
- [OpenIE](https://stanfordnlp.github.io/CoreNLP/openie.html)
- [RESIN](https://github.com/RESIN-KAIROS/RESIN-pipeline-public)
- [ZShot](https://github.com/IBM/zshot)
- [ZS4IE](https://github.com/BBN-E/ZS4IE)
- [OmniEvent](https://github.com/THU-KEG/OmniEvent)
