
<div align="center">

<h1>Prompting ChatGPT in MNER: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge</h1>

[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/prompt-chatgpt-in-mner-improved-multimodal/multi-modal-named-entity-recognition-on-3)](https://paperswithcode.com/sota/multi-modal-named-entity-recognition-on-3?p=prompt-chatgpt-in-mner-improved-multimodal)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/prompt-chatgpt-in-mner-improved-multimodal/multi-modal-named-entity-recognition-on)](https://paperswithcode.com/sota/multi-modal-named-entity-recognition-on?p=prompt-chatgpt-in-mner-improved-multimodal)

![Image](main.png)

</div>

Here are code and dataset for our Findings of EMNLP 2023 paper: [Prompting ChatGPT in MNER: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge](https://aclanthology.org/2023.findings-emnlp.184/)

# News🔥

 - 📆 **[Jun. 2024]** [A new research](https://arxiv.org/abs/2406.07268) has been released. We propose a new Segmented Multimodal Named Entity Recognition (SMNER) task and construct the corresponding Twitter-SMNER dataset. Code and Twitter-SMNER dataset [coming soon](https://github.com/JinYuanLi0012/RiVEG)~
 - 📆 **[May. 2024]** [RiVEG](https://github.com/JinYuanLi0012/RiVEG) (the sequel to PGIM about GMNER) has been accepted to ACL 2024 Findings.
 - 📆 **[Oct. 2023]** PGIM has been accepted to EMNLP 2023 Findings.

# Dataset
To ease the code running, you can find our pre-processed datasets at [here](https://www.modelscope.cn/datasets/Dexter1202/PGIM/files). And the predefined artificial samples are [here](data/ManualAnnotation).

# Requirement
```
python == 3.7
torch == 1.13.1
transformers == 4.30.2
modelscope == 1.7.1
```

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
@inproceedings{li2023prompting,
  title={Prompting ChatGPT in MNER: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge},
  author={Li, Jinyuan and Li, Han and Pan, Zhuo and Sun, Di and Wang, Jiahao and Zhang, Wenkun and Pan, Gang},
  booktitle={Findings of the Association for Computational Linguistics (EMNLP), 2023},
  year={2023}
}

@inproceedings{li2024llms,
  title={LLMs as Bridges: Reformulating Grounded Multimodal Named Entity Recognition},
  author={Li, Jinyuan and Li, Han and Sun, Di and Wang, Jiahao and Zhang, Wenkun and Wang, Zan and Pan, Gang},
  booktitle={Findings of the Association for Computational Linguistics (ACL), 2024},
  year={2024}
}

@article{li2024advancing,
  title={Advancing Grounded Multimodal Named Entity Recognition via LLM-Based Reformulation and Box-Based Segmentation},
  author={Li, Jinyuan and Li, Ziyan and Li, Han and Yu, Jianfei and Xia, Rui and Sun, Di and Pan, Gang},
  journal={arXiv preprint arXiv:2406.07268},
  year={2024}
}
```

# Acknowledgement
Our code is built upon the open-sourced [AdaSeq](https://github.com/modelscope/AdaSeq) and [MoRe](https://github.com/modelscope/AdaSeq/tree/master/examples/MoRe), Thanks for their great work!
