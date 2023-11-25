PGIM is based on AdaSeq, AdaSeq project is based on Python version >= 3.7 and PyTorch version >= 1.8.

Step 1: Installation

git clone https://github.com/modelscope/adaseq.git
cd adaseq
pip install -r requirements.txt -f https://modelscope.oss-cn-beijing.aliyuncs.com/releases/repo.html


Step 2: Copy PGIM folder into .../adaseq/examples/

-adaseq
---|examples
-----|PGIM
-------|twitter-15-txt.yaml
-------|twitter-17-txt.yaml


Step 3：Replace the original adaseq folder with our adaseq folder

-adaseq
---|.git
---|.github
---|adaseq   <-- (Use our adaseq replace it)  
---|docs
---|examples
---|scripts
---|tests
---|tools

Step 4: Training Model

-For Baseline:
	python -m scripts.train -c examples/PGIM/twitter-15.yaml
	python -m scripts.train -c examples/PGIM/twitter-17.yaml
-For PGIM:
	python -m scripts.train -c examples/PGIM/twitter-15-txt.yaml
	python -m scripts.train -c examples/PGIM/twitter-17-txt.yaml