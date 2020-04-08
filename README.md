<p align="center">
<img src="https://xuanyidong.com/resources/images/AutoDL-log.png" width="400"/>
</p>

---------
[![MIT licensed](https://img.shields.io/badge/license-MIT-brightgreen.svg)](LICENSE.md)

Automated Deep Learning (AutoDL-Projects) is an open source, lightweight, but useful project for researchers.
This project implemented several neural architecture search (NAS) and hyper-parameter optimization (HPO) algorithms.

**Who should consider using AutoDL-Projects**

- Beginners who want to **try different AutoDL algorithms**
- Engineers who want to **try AutoDL** to investigate whether AutoDL works on your projects
- Researchers who want to **easily** implement and experiement **new** AutoDL algorithms.

**Why should we use AutoDL-Projects**
- Simple library dependencies
- All algorithms are in the same codebase
- Active maintenance


## AutoDL-Projects Capabilities

At the moment, this project provides the following algorithms and scripts to run them. Please see the details in the link provided in the description column.


<table>
 <tbody>
    <tr align="center" valign="bottom">
      <th>Type</th>
      <th>ABBRV</th>
      <th>Algorithms</th>
      <th>Description</th>
    </tr>
    <tr> <!-- (1-st row) -->
    <td rowspan="6" align="center" valign="middle" halign="middle"> NAS </td>
    <td align="center" valign="middle"> TAS </td>
    <td align="center" valign="middle"> <a href="https://arxiv.org/abs/1905.09717">Network Pruning via Transformable Architecture Search</a> </td>
    <td align="center" valign="middle"> <a href="https://github.com/D-X-Y/AutoDL-Projects/tree/master/docs/NIPS-2019-TAS.md">NIPS-2019-TAS.md</a> </td>
    </tr>
    <tr> <!-- (2-nd row) -->
    <td align="center" valign="middle"> DARTS </td>
    <td align="center" valign="middle"> <a href="https://arxiv.org/abs/1806.09055">DARTS: Differentiable Architecture Search</a> </td>
    <td align="center" valign="middle"> <a href="https://github.com/D-X-Y/AutoDL-Projects/tree/master/docs/ICLR-2019-DARTS.md">ICLR-2019-DARTS.md</a> </td>
    </tr>
    <tr> <!-- (3-nd row) -->
    <td align="center" valign="middle"> GDAS </td>
    <td align="center" valign="middle"> <a href="https://arxiv.org/abs/1910.04465">Searching for A Robust Neural Architecture in Four GPU Hours</a> </td>
    <td align="center" valign="middle"> <a href="https://github.com/D-X-Y/AutoDL-Projects/tree/master/docs/CVPR-2019-GDAS.md">CVPR-2019-GDAS.md</a> </td>
    </tr>
    <tr> <!-- (4-rd row) -->
    <td align="center" valign="middle"> SETN </td>
    <td align="center" valign="middle"> <a href="https://arxiv.org/abs/1910.05733">One-Shot Neural Architecture Search via Self-Evaluated Template Network</a> </td>
    <td align="center" valign="middle"> <a href="https://github.com/D-X-Y/AutoDL-Projects/tree/master/docs/ICCV-2019-SETN.md">ICCV-2019-SETN.md</a> </td>
    </tr>
    <tr> <!-- (5-th row) -->
    <td align="center" valign="middle"> NAS-Bench-201 </td>
    <td align="center" valign="middle"> <a href="https://openreview.net/forum?id=HJxyZkBKDr"> NAS-Bench-201: Extending the Scope of Reproducible Neural Architecture Search</a> </td>
    <td align="center" valign="middle"> <a href="https://github.com/D-X-Y/AutoDL-Projects/tree/master/docs/NAS-Bench-201.md">NAS-Bench-201.md</a> </td>
    </tr>
    <tr> <!-- (6-th row) -->
    <td align="center" valign="middle"> ... </td>
    <td align="center" valign="middle"> ENAS / REA / REINFORCE / BOHB </td>
    <td align="center" valign="middle"> <a href="https://github.com/D-X-Y/AutoDL-Projects/tree/master/docs/NAS-Bench-201.md">NAS-Bench-201.md</a> </td>
    </tr>
    <tr> <!-- (start second block) -->
    <td rowspan="1" align="center" valign="middle" halign="middle"> HPO </td>
    <td align="center" valign="middle"> HPO-CG </td>
    <td align="center" valign="middle"> Hyperparameter optimization with approximate gradient </td>
    <td align="center" valign="middle"> coming soon </a> </td>
    </tr>
    <tr> <!-- (start third block) -->
    <td rowspan="1" align="center" valign="middle" halign="middle"> Basic </td>
    <td align="center" valign="middle"> ResNet </td>
    <td align="center" valign="middle"> Deep Learning-based Image Classification </td>
    <td align="center" valign="middle"> <a href="https://github.com/D-X-Y/AutoDL-Projects/tree/master/docs/BASELINE.md">BASELINE.md</a> </a> </td>
    </tr>
 </tbody>
</table>


## History of this repo

At first, this repo is `GDAS`, which is used to reproduce results in Searching for A Robust Neural Architecture in Four GPU Hours.
After that, more functions and more NAS algorithms are continuely added in this repo. After it supports more than five algorithms, it is upgraded from `GDAS` to `NAS-Projects`.
Now, since both HPO and NAS are supported in this repo, it is upgraded from `NAS-Projects` to `AutoDL-Projects`.


## Requirements and Preparation

Please install `Python>=3.6` and `PyTorch>=1.3.0`. (You could also run this project in lower versions of Python and PyTorch, but may have bugs).
Some visualization codes may require `opencv`.

CIFAR and ImageNet should be downloaded and extracted into `$TORCH_HOME`.
Some methods use knowledge distillation (KD), which require pre-trained models. Please download these models from [Google Drive](https://drive.google.com/open?id=1ANmiYEGX-IQZTfH8w0aSpj-Wypg-0DR-) (or train by yourself) and save into `.latent-data`.

## Experiments
### Results on CIFAR10
#### Run on NAS-Projects
|Model| Error(%)| Search cost(GPU days)	|Genotypes|	Val_acc of arch|	Search-seed|
|:--:|:--:|:--:|:--:|:--:|:--:|
|DARTS-V1|	3.00±0.14	|0.25	|Paper	|-|	-|
|DARTS-V1|	-	|0.26|	Searched 1|	89.24|	90627|
|DARTS-V1|	-	|0.26|	Searched 2|	89.11|	77047|
|**DARTS-V1**|	3.56±0.04	|0.26	|Searched 3	|89.27	|90451|
|DARTS-V1|	-	|0.26	|Searched 4|	89.10|	2189|
|DARTS-V2|	2.76±0.09|	1|	Paper	|-	|-|
|DARTS-V2|	-|	1.32|	Searched 1	|89.13	|52665|
|DARTS-V2|	-	|1.33	|Searched 2	|89.16	|68513|
|**DARTS-V2**|	|1.43	|Searched 3|	89.20|	33376|
|DARTS-V2|	-|	1.33	|Searched 4	|89.17|	74480|

The command to search architectures.
```
CUDA_VISIBLE_DEVICES=0 bash ./scripts-search/DARTS1V-search-NASNet-space.sh cifar10 -1
CUDA_VISIBLE_DEVICES=0 bash ./scripts-search/DARTS2V-search-NASNet-space.sh cifar10 -1
```
The command to train.
```
CUDA_VISIBLE_DEVICES=0 bash ./scripts/nas-infer-train.sh cifar10  DARTS_V1 96 -1
CUDA_VISIBLE_DEVICES=0 bash ./scripts/nas-infer-train.sh cifar10  DARTS_V2 96 -1
```

|Model| Error(%)| Search cost(GPU days)	|Genotypes|	Val_acc of arch|	Search-seed|
|:--:|:--:|:--:|:--:|:--:|:--:|
|GDAS|	2.93|	0.21|	Paper|	-|	-|
|GDAS|	2.82(Reproduced)|	-|	Paper|	-|	-|
|GDAS|	-|	0.19|	Searched 1	|78.26	|11110|
|GDAS|	-|	0.19|	Searched 2	|78.23	|21945|
|GDAS|	-|	0.19|	Searched 3	|78.03	|39472|
|**GDAS**|	2.89±0.05	|0.19|	Searched 4|	78.60|	49342|

The command to search architectures.
```
CUDA_VISIBLE_DEVICES=0 bash ./scripts-search/GDAS-search-NASNet-space.sh cifar10 -1
```
The command to train.
```
CUDA_VISIBLE_DEVICES=0 bash ./scripts/nas-infer-train.sh cifar10  GDAS_V1 96 -1
```

|Model| Error(%)| Search cost(GPU days)	|Genotypes|	Val_acc of arch|	Search-seed|
|:--:|:--:|:--:|:--:|:--:|:--:|
|DARTS+|	2.50±0.11|	0.4|	Paper|	-|	-|
|DARTS+|	-|	0.42|	Searched 1	|84.06|	67841|
|DARTS+|	-|	0.56|	Searched 2|	85.41|	68221|
|**DARTS+**|	2.97±0.07|	0.51	|Searched 3	|85.78|	99594|
|DARTS+|	-|	0.49	|Searched 4	|84.75	|22713|
|DARTS+(V1)|	-	|0.14|	Searched 1	|86.02|	38979|
|DARTS+(V1)|	-	|0.16| Searched 2	|85.56	|57053|
|**DARTS+(V1)**|	3.19±0.00|	0.17	|Searched 3|87.20	|34853|
|DARTS+(V1)|	-|	0.14	|Searched 4|	85.28|	21462|

The command to search and train are same as DARTS.

Run on [quark0/darts](https://github.com/quark0/darts)
|Model| Error(%)| Search cost(GPU days)	|Genotypes|	Val_acc of arch|	Search-seed|
|:--:|:--:|:--:|:--:|:--:|:--:|
|DARTS-V1|	3.00±0.14	|0.25|	Paper	|-|	-|
|DARTS-V1|	-	|0.38|	Searched 1	|88.97|	2|
|DARTS-V1|	-	|0.35|	Searched 2	|89.08|	444|
|**DARTS-V1**|	2.99±0.04|	0.35	|Searched 3	|89.31	|666|
|DARTS-V1|	-	|0.34|	Searched 4	|89.30	|999|
|DARTS-V2|	2.76±0.09|	1	|Paper|	-	|-|
|DARTS-V2|	-	|0.83	|Searched 1	|89.23|	2|
|DARTS-V2|	-	|1.04	|Searched 2	|89.17|	555|
|**DARTS-V2**|	3.02±0.16|	0.79	|Searched 3	|89.34|	777|
|DARTS-V2|	-|	0.79|	Searched 4	|89.02|	888|

The command to search architectures.
```
python train_search.py     # for conv cells on CIFAR-10(DARTS-V1)
python train_search.py --unrolled     # for conv cells on CIFAR-10(DARTS-V2)
```
The command to train.
```
python train.py --auxiliary --cutout            # CIFAR-10
```
|Model| Error(%)| Search cost(GPU days)	|Genotypes|	Val_acc of arch|	Search-seed|
|:--:|:--:|:--:|:--:|:--:|:--:|
|DARTS+|	2.50±0.11|	0.4|	Paper|	-|	-|
|DARTS+|	-	|0.58	|Searched 1|	85.64|233|
|DARTS+|	-	|0.52	|Searched 2	|85.99	|694|
|**DARTS+**|	2.97±0.07	|0.73	|Searched 3|	88.48|	1113|
|DARTS+|	-	|0.54	|Searched 4|	86.38|	3763|
|DARTS+(V1)|	-	|0.40|	Searched 1	|85.64|	38|
|DARTS+(V1)|	-	|0.61|	Searched 2	|85.99|	2981|
|**DARTS+(V1)**|	2.69±0.06	|0.31|	Searched 3	|86.39	|8632|
|DARTS+(V1)|	-|	0.23|	Searched 4	|83.94	|3659|

The command to search and train the DARTS+ are same as DARTS.

P.S. The searched architecture in **DARTS+(V1)** is out of memory when training by the [quark0/darts](https://github.com/quark0/darts). So I train it by the NAS-Projects code. The command is 
```
CUDA_VISIBLE_DEVICES=0 bash ./scripts/nas-infer-train.sh cifar10  DARTS_V1 96 -1
```

#### Comparison
|Model| Error(%)| Search cost(GPU days)	|Genotypes|	Params(M)|	Train cost()GPU days|
|:--:|:--:|:--:|:--:|:--:|:--:|
|DARTS-V1|	3.00±0.14|	0.25|	Paper|	3.3|	-|
|DARTS-V2|	2.76±0.09	|1	| Paper|	3.3|	-|
|GDAS|	2.93	|0.21	|Paper 	|3.4	|-|
|NASP|	2.83±0.09	|0.1	|Paper |	3.3|	-|
|NASP(12ops)|	2.44±0.04	|0.2	|Paper|	7.4|	-|
|DARTS-V1|	2.99±0.04	|0.35|	Our Searched	([quark0/darts](https://github.com/quark0/darts))|3.20|	1.71|
|DARTS-V1|	3.56±0.04	|0.26|	Our Searched	(NAS-Projects)|1.73|	1.33|
|DARTS-V2|	3.02±0.16	|0.79|	Our Searched	([quark0/darts](https://github.com/quark0/darts))|3.17|	1.46|
|DARTS-V2|		|1.43|	Our Searched	(NAS-Projects)||	|
|GDAS|	2.89±0.05	|0.19|	Our Searched |3.77	|2.25|
|NASP|	3.34±0.07	|0.25	|Our Searched |	2.40|	1.29|
|NASP(12ops)|	2.44±0.04	|0.25	|Our Searched|	8.27|	1.5|

## Citation

If you find that this project helps your research, please consider citing some of the following papers:
```
@inproceedings{dong2020nasbench201,
  title     = {NAS-Bench-201: Extending the Scope of Reproducible Neural Architecture Search},
  author    = {Dong, Xuanyi and Yang, Yi},
  booktitle = {International Conference on Learning Representations (ICLR)},
  url       = {https://openreview.net/forum?id=HJxyZkBKDr},
  year      = {2020}
}
@inproceedings{dong2019tas,
  title     = {Network Pruning via Transformable Architecture Search},
  author    = {Dong, Xuanyi and Yang, Yi},
  booktitle = {Neural Information Processing Systems (NeurIPS)},
  year      = {2019}
}
@inproceedings{dong2019one,
  title     = {One-Shot Neural Architecture Search via Self-Evaluated Template Network},
  author    = {Dong, Xuanyi and Yang, Yi},
  booktitle = {Proceedings of the IEEE International Conference on Computer Vision (ICCV)},
  pages     = {3681--3690},
  year      = {2019}
}
@inproceedings{dong2019search,
  title     = {Searching for A Robust Neural Architecture in Four GPU Hours},
  author    = {Dong, Xuanyi and Yang, Yi},
  booktitle = {Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  pages     = {1761--1770},
  year      = {2019}
}
```

# Others

If you want to contribute to this repo, please see [CONTRIBUTING.md](.github/CONTRIBUTING.md).
Besides, please follow [CODE-OF-CONDUCT.md](.github/CODE-OF-CONDUCT.md).

# License
The entire codebase is under [MIT license](LICENSE.md)
