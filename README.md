# M2ST

## What is M2ST?

![Figure1_overview.png](https://github.com/LYxiaotai/M2ST/blob/main/Figure1_overview.png)

M2ST, a Graph ATtention auto-Encoder framework featuring two Masking strategies: masked feature reconstruction and re-mask decoding. 

* The graph attention module in M2ST enables adaptive learning of local spatial neighbors, while the masking strategies enhance model robustness, resulting in stable latent representations with more core biological information. 

* M2ST adopts an edge removal strategy to construct an enhanced spatial graph, which is more specific for the domain identification task, facilitating clearer delineation of domain boundaries. 

* By employing mask strategies and integrating gene expression data with the enhanced spatial graph, M2GATE learns stable latent representations that improve spatial domain identification and downstream analyses, such as tissue structure visualization, Uniform Manifold Approximation and Projection (UMAP) visualization, spatial trajectory inference, pseudo-spatiotemporal map (pSM) analysis and discovery of domain-specific marker genes.


## How to use M2ST?

### 1. Requirements

- Python 3.9
- R 4.2.2
- Quick Installation： M2ST is implemented in the pytorch framework (tested on Python 3.9.19). We recommend that users run M2ST on CUDA.
#### Before install the Python dependencies, we recommend that users create a new conda enviroment and R environment.
-   `Conda create -n env python=3.9`
-   `conda install r-base`
#### Install Python dependencies
-   `pip install -r requirement.txt`
#### Install R dependencies (requires R environment)
M2ST also calls the "mclust" package in the R language. We recommend use the R Version 4.2.2.
The use of the mclust algorithm requires the rpy2 package and the mclust package. See https://pypi.org/project/rpy2/ and https://cran.r-project.org/web/packages/mclust/index.html.
-   `conda install r-mclust`
```

# R Version 4.2.2
install.packages("mclust")    # recommend mclust version 6.0.1

```


### 2. Tutorial

(1) Download the [M2ST_F.py](https://github.com/LYxiaotai/M2ST/blob/main) and [gat_conv2.py](https://github.com/LYxiaotai/M2ST/blob/main).

(2) Tutorial for domain identification on 10x Visium human dorsolateral prefrontal cortex (DLPFC) dataset can be found here: [Train_151674.ipynb](https://github.com/LYxiaotai/M2ST/blob/main/Train_151674.ipynb).

* The datasets for the Tutorial [Train_151674.ipynb](https://github.com/LYxiaotai/M2ST/blob/main/Train_151674.ipynb) can be found [here](https://github.com/LYxiaotai/M2ST/tree/main/data/151674).
* The domain identification results of the Tutorial [Train_151674.ipynb](https://github.com/LYxiaotai/M2ST/blob/main/Train_151674.ipynb) can be found [here](https://github.com/LYxiaotai/M2ST/tree/main/data/results).
* When facing to determining the number of clusters without prior knowledge, we recommend selecting the number of clusters by identifying the maximum score within a range of potential values, using metrics such as the Silhouette score. We have provided the function cluster_select() to help select the highest Silhouette score in [M2ST_F.py](https://github.com/LYxiaotai/M2ST/blob/main/M2ST_F.py).
* Additionally, recent advances in the field of statistics, nonparametric Bayesian, such as the nonparametric Potts prior, offer inferring spatial domains in a fully data-driven manner. A related reference is Yan and Luo (2024, Bayesian integrative region segmentation in spatially resolved transcriptomic studies, JASA) (https://doi.org/10.1080/01621459.2024.2308323).



