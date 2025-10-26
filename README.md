# Reproduction version of PropCare
- This repository was created to reproduce [PropCare model](https://arxiv.org/abs/2310.20388), so that we can develop new model: [Here](https://github.com/JeongHo-SEO/ARC-Rec)
- Some environments were changed due to the upgraded version after the [PropCare code](https://github.com/mediumboat/PropCare) was released.
- The updated Requirements (Environment) are listed in the "Requirements.txt" file.
- I used dataset only ML-100K.
- Datasets are not served in this repository. Download [Here](https://drive.google.com/drive/folders/1YcXz8f0Uck6lcVRze51qLjvAcdnwHiox?usp=sharing)
- The dataset path setting is: raw_data/arXiv-2012.09442v2/anc/data/synthetic/ML_100k_logrank100_offset5.0_scaling1.0"
- [Colab Code](https://colab.research.google.com/drive/1PlTxo5HDECcR560vEK-gib69IAJEv4kt?usp=sharing): Uncompleted version. You shoud only consider about the path of dataset.
---
# Code repository for PropCare

This is the implementation of paper "Estimating Propensity for Causality-based Recommendation without Exposure Data" presented in NeurIPS 2023 ([link to paper](https://arxiv.org/abs/2310.20388)).

## Description of each file:

baselines.py: including codes for DLCE model (or some other recommendation models) (Many thanks to Masahiro Sato for their open source codes)

evaluator.py: evaluation code to compute CP@10, CP@100 and CDCG (Many thanks to Masahiro Sato for their open source codes)

main.py: the entrance of the program

models.py: codes for our proposed PropCare model

train.py: training codes, also including data loading related codes

/model: the check point of optimzed models.

## Requirements (Environment)
	python >= 3.6
	tensorflow >= 2.2.0
  	numpy
  	pandas
  	tqdm 
  	pathlib 


## Dataset & How to run:

1. Since the semi-simulated dataset is quite large (~2GB each), you should download from the original source.
Download the raw data and code for generating semi-simulated from https://arxiv.org/abs/2008.04563 (DH) and https://arxiv.org/abs/2012.09442 (ML), generate the dataset as guided in their `README` files.

2. Modify the path to dataset in `prepare_data` of train.py

3. Set all parameters in main.py

4. Execute "python -u main.py --dataset d" for DH_original dataset, "python -u main.py --dataset p" for DH_personalized dataset, "python -u main.py --dataset ml" for ML dataset.

   The check points of optimzed models for each dataset are avaliable in /model.

## Contact
For any questions, please contact me (zzliu[DOT]2020[AT]phdcs[DOT]smu[DOT]edu[DOT]sg)
