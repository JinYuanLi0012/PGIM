# Prompting ChatGPT in MNER: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/prompt-chatgpt-in-mner-improved-multimodal/multi-modal-named-entity-recognition-on)](https://paperswithcode.com/sota/multi-modal-named-entity-recognition-on?p=prompt-chatgpt-in-mner-improved-multimodal)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/prompt-chatgpt-in-mner-improved-multimodal/multi-modal-named-entity-recognition-on-3)](https://paperswithcode.com/sota/multi-modal-named-entity-recognition-on-3?p=prompt-chatgpt-in-mner-improved-multimodal)


Here are code and dataset for our Findings of EMNLP 2023 paper: [Prompting ChatGPT in MNER: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge]([https://arxiv.org/abs/2305.12212](https://aclanthology.org/2023.findings-emnlp.184/))

![My Image](main.png)

# Dataset
To ease the code running, you can find our pre-processed datasets at [here](https://www.modelscope.cn/datasets/Dexter1202/PGIM/files). And the predefined artificial samples are [here](data/ManualAnnotation).

# Usage
PGIM is based on [AdaSeq](https://github.com/modelscope/AdaSeq), AdaSeq project is based on Python version >= 3.7 and PyTorch version >= 1.8.

## Step 1: Installation
```
git clone https://github.com/modelscope/adaseq.git
cd adaseq
pip install -r requirements.txt -f https://modelscope.oss-cn-beijing.aliyuncs.com/releases/repo.html
```

## Step 2: Copy PGIM folder into .../adaseq/examples/
```
-adaseq
---|examples
-----|PGIM
-------|twitter-15-txt.yaml
-------|twitter-17-txt.yaml
```

## Step 3: Replace the original adaseq folder with our adaseq folder
```
-adaseq
---|.git
---|.github
---|adaseq   <-- (Use our adaseq replace it)  
---|docs
---|examples
---|scripts
---|tests
---|tools
```

## Step 4: Training Model
-For Baseline:
```
	python -m scripts.train -c examples/PGIM/twitter-15.yaml
	python -m scripts.train -c examples/PGIM/twitter-17.yaml
```
-For PGIM:
```
	python -m scripts.train -c examples/PGIM/twitter-15-PGIM.yaml
	python -m scripts.train -c examples/PGIM/twitter-17-PGIM.yaml
```

# Citation
If you find PGIM useful in your research, please consider citing:
```
@inproceedings{li-etal-2023-prompting,
    title = "Prompting {C}hat{GPT} in {MNER}: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge",
    author = "Li, Jinyuan  and
      Li, Han  and
      Pan, Zhuo  and
      Sun, Di  and
      Wang, Jiahao  and
      Zhang, Wenkun  and
      Pan, Gang",
    editor = "Bouamor, Houda  and
      Pino, Juan  and
      Bali, Kalika",
    booktitle = "Findings of the Association for Computational Linguistics: EMNLP 2023",
    month = dec,
    year = "2023",
    address = "Singapore",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2023.findings-emnlp.184",
    pages = "2787--2802",
    abstract = "Multimodal Named Entity Recognition (MNER) on social media aims to enhance textual entity prediction by incorporating image-based clues. Existing studies mainly focus on maximizing the utilization of pertinent image information or incorporating external knowledge from explicit knowledge bases. However, these methods either neglect the necessity of providing the model with external knowledge, or encounter issues of high redundancy in the retrieved knowledge. In this paper, we present PGIM {---} a two-stage framework that aims to leverage ChatGPT as an implicit knowledge base and enable it to heuristically generate auxiliary knowledge for more efficient entity prediction. Specifically, PGIM contains a Multimodal Similar Example Awareness module that selects suitable examples from a small number of predefined artificial samples. These examples are then integrated into a formatted prompt template tailored to the MNER and guide ChatGPT to generate auxiliary refined knowledge. Finally, the acquired knowledge is integrated with the original text and fed into a downstream model for further processing. Extensive experiments show that PGIM outperforms state-of-the-art methods on two classic MNER datasets and exhibits a stronger robustness and generalization capability.",
}
```

# Acknowledgement
Our code is built upon the open-sourced [AdaSeq](https://github.com/modelscope/AdaSeq) and [MoRe](https://github.com/modelscope/AdaSeq/tree/master/examples/MoRe), Thanks for their great work!
