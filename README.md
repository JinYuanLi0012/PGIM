# Prompting ChatGPT in MNER: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge
Here are code and dataset for our Findings of EMNLP 2023 paper: [Prompting ChatGPT in MNER: Enhanced Multimodal Named Entity Recognition with Auxiliary Refined Knowledge](https://arxiv.org/abs/2305.12212)

# Usage
PGIM is based on [AdaSeq](https://github.com/modelscope/AdaSeq), AdaSeq project is based on Python version >= 3.7 and PyTorch version >= 1.8.

# Dataset
To ease the code running, you can find our pre-processed datasets at [here](https://www.modelscope.cn/datasets/Dexter1202/PGIM/files). And the predefined artificial samples are [here](data/ManualAnnotation).


# Step 1: Installation
```
git clone https://github.com/modelscope/adaseq.git
cd adaseq
pip install -r requirements.txt -f https://modelscope.oss-cn-beijing.aliyuncs.com/releases/repo.html
```

# Step 2: Copy PGIM folder into .../adaseq/examples/
```
-adaseq
---|examples
-----|PGIM
-------|twitter-15-txt.yaml
-------|twitter-17-txt.yaml
```

# Step 3：Replace the original adaseq folder with our adaseq folder
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

# Step 4: Training Model
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
@article{li2023prompt,
  title={Prompt ChatGPT In MNER: Improved multimodal named entity recognition method based on auxiliary refining knowledge from ChatGPT},
  author={Li, Jinyuan and Li, Han and Pan, Zhuo and Pan, Gang},
  journal={arXiv preprint arXiv:2305.12212},
  year={2023}
}
```

# Acknowledgement
Our code is built upon the open-sourced [AdaSeq](https://github.com/modelscope/AdaSeq) and [MoRe](https://github.com/modelscope/AdaSeq/tree/master/examples/MoRe), Thanks for their great work!
