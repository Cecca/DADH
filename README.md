# Deep Adversarial Discrete Hashing for Cross-Modal Retrieval

## Introduction

This is the source code of ICMR 2020 paper "Deep Adversarial Discrete Hashing for Cross-Modal Retrieval".

## Requirements

- Python 3.7.2
- Pytorch 1.6.0
- torchvision 0.7.0
- CUDA 10.1 and cuDNN 7.6.4
```shell
##Install required libraries##
pip install -r requirements.txt
```
##  Train

```shell
##before train##
python -m visdom.server
##train##
python main.py train [--flag DATASET] [--batch_size BATCH_SIZE] [--lr LR]
                     [--valid_freq FRQ] [--output_dim CODE_LENGTH] [--lamb LAMBDA]
                     [--alpha ALPHA] [--gamma GAMMA] [--beta BETA] [--mu MU]
                     [--margin MARGIN] [--max_epoch MAX_ITER] [--vis_env VIS_ENV] 


optional arguments:
  --flag DATASET        Dataset name.('mir' or 'nus')
  --batch_size BATCH_SIZE
                        Batch size.(default: 128)
  --lr LR               Learning rate.(default: 1e-3)
  --valid_freq FRQ      Valid frequency.(default: 1)
  --output_dim CODE_LENGTH
                        Binary hash code length.(default: 16,32,64)
  --lamb LAMBDA         Hyper-parameter.(default: 1)
  --alpha ALPHA         Hyper-parameter.(default: 10)
  --gamma GAMMA         Hyper-parameter.(default: 1)
  --beta BETA           Hyper-parameter.(default: 1)
  --mu MU               Hyper-parameter.(default: 1e-5)
  --margin MARGIN       Hyper-parameter.(default: 0.4)
  --max_epoch MAX_ITER  Number of iterations.(default: 300)
  --vis_env VIS_ENV     Visdom environment name.(default: 'main')
```

## Test

```shell
##test##
python main.py test [--flag DATASET] [--output_dim CODE_LENGTH]
```

## Datasets
- CNN-F: https://pan.baidu.com/s/17R7t1qKNskIDWzLhALYFPg 提取码：cou4 
- NUS-WIDE: <br>
           -Google: https://drive.google.com/file/d/125G-B7sIQPVIcRk4W7qR-tkc6gcBP-mX/view?usp=sharing <br>
           -Baidu: https://pan.baidu.com/s/1Hb4FzOOxqJjR4tDAP5C8rw 提取码：v60x 
- MIRFlickr25K: <br>
           -Google: https://drive.google.com/file/d/1Eca2meBpmhnfezkUVqQJo0tJnEpwQwi2/view?usp=sharing <br>
           -Baidu: https://pan.baidu.com/s/14JrUH2AdnvDV1ezs0Qxc5w 提取码：22fs 

Note: We extracted 4096-d features of the images in the datasets using CNN-F~\cite{Chatfield2014} pre-trained on ImageNet.

## Framework

![framework](framework.png)

## Result

<img src="result.png" style="zoom: 67%;" />

## Note

Our codes were modified from the implementation of "Adversary Guided Asymmetric Hashing for Cross-Modal Retrieval", written by Wen Gu. Please cite the  two papers (AGAH and DADH) when you use the codes.

## Citing DADH & AGAH

```
@inproceedings{Bai2020,
  author={Cong Bai, Chao Zeng, Qing Ma, Jinglin Zhang and Shengyong Chen.},
  booktitle={Proceedings of the 2020 on International Conference on Multimedia Retrieval},
  pages={525-531},
  title={Deep Adversarial Discrete Hashing for Cross-Modal Retrieval},
  year={2020},
}
```
```
@inproceedings{Gu2019,
author = {Gu, Wen and Gu, Xiaoyan and Gu, Jingzi and Li, Bo and Xiong, Zhi and Wang, Weiping},
booktitle = {Proceedings of the ACM International Conference on Multimedia Retrieval},
pages = {159--167},
title = {{Adversary guided asymmetric hashing for cross-modal retrieval}},
year = {2019}
}
```
