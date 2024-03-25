## Installation and Preparation
## 安装和准备

![Python](https://img.shields.io/badge/Python->=3.6-Blue?logo=python)  ![Pytorch](https://img.shields.io/badge/PyTorch->=1.0.0-Orange?logo=pytorch) ![mmcv](https://img.shields.io/badge/mmcv-%3E%3D0.4.0-green)


### Requirements
### 安装依赖
SceneSeg is currently very easy to install before the introduction of **feature extractor**

- Python 3.6+
- PyTorch 1.0 or higher
- [mmcv](https://github.com/open-mmlab/mmcv)

a. Install PyTorch and torchvision following the [official instructions](https://pytorch.org/), e.g.,

```sh
conda install pytorch torchvision -c pytorch
```

b. Clone the SceneSeg repository.

```sh
git clone https://github.com/AnyiRao/SceneSeg.git
cd SceneSeg
```
c. Install Python Packages

```sh
pip install -r docs/requirements.txt
```

### Folder Structure
### 文件夹结构
```sh
|-data ## the data_root for experiments
|-run  ## to store experiments
|-pre  ## for preprocess
|-lgss
|   |-src
|   |-config
|   |-utilis
|   |-run.py
|   |-gen_csv.py
```
### Download Pretrained Models
### 下载预训练模型
Pretrained models are at [Google Drive](https://drive.google.com/open?id=1F-uqCKnhtSdQKcDUiL3dRcLOrAxHargz).
Please follow the provided folder structure and put it under ``run``.
请按照原本提供的文件夹结构， 将预训练模型下载到 ``run`` 文件夹下，

### Prepare Datasets for Scene318
### 准备数据集
Annotation and metadata are at [Google Drive](https://drive.google.com/open?id=1F-uqCKnhtSdQKcDUiL3dRcLOrAxHargz). The full movienet annotation including, debut year, cast, director info and so on can be downloaded from [OpenDataLab](https://opendatalab.com/MovieNet/download)
声明和元数据在 [Google Drive](https://drive.google.com/open?id=1F-uqCKnhtSdQK
) 下载。 完整的 movienet声明包括，发行年份，演员，导演等信息可以从 [OpenDataLab](https://opendatalab.com/MovieNet/download) 下载。

The intermediate features ``place_feat, cast_feat, act_feat, aud_feat`` are located at [OneDrive](https://mycuhk-my.sharepoint.com/:f:/g/personal/1155113941_link_cuhk_edu_hk/Eu52Dx-I5M5KhAQKXnwg2oQBV4icIe_zpziOQkqAo1_5XA?e=9hYk28) due to the limited free size of Google Drive. They can be extracted with unzip e.g., ``unzip act_feat.zip``. 

中间特征 ``place_feat, cast_feat, act_feat, aud_feat`` 位于 [OneDrive](https://mycuh-my.sharepoint.com/:f:/g/personal/1155113941_link_cuhk_edu_hk/Eu52Dx-I5M5KhAQKXnwg2oQBV4icIe_zpziOQkqAo1_5XA?e=9hYk28)
由于 Google Drive 限制了免费空间，所以需要解压。
例如，解压 ``act_feat.zip`` 文件。

Put ``label318`` ``shot_movie318`` ``meta/split318.json``, 
intermediate features ``place_feat, cast_feat, act_feat, aud_feat`` under ``data``. 
将 ``label318`` ``shot_movie318`` ``meta/split318.json``，中间特征 ``place_feat, cast_feat, act_feat, aud_feat`` 放在 ``data`` 文件夹下。

#### Explanation
#### 解释
```label318``` is the scene transit (**1**) or not (**0**) label for each shot. ```shot_movie318``` is the shot and frame correspondence to recover the time of each scene. They will be automatically handled by the processing codes e.g., the ``data_pre`` function in ``src/data/all.py``

```label318``` 是每个shot的场景过渡（**1**）或非过渡（**0**）标签。 ```shot_movie318``` 是shot和帧的对应关系，用于恢复每个场景的时间。
这些文件会自动处理，例如 ``src/data/all.py`` 中的 ``data_pre`` 函数。

### Prepare Your Own Dataset
### 准备自己的数据集
If you run our demo, you don't need to prepare. Just run our [three lines](./GETTING_STARTED.md#demo).If you wish to use the method's full functions, you may need to organize your data like ours.
如果运行我们的demo，你不需要准备。只需运行 [三个命令](./GETTING_STARTED.md#demo)。如果你希望使用方法的完整功能，你可能需要像我们一样组织你的数据。
