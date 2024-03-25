# SceneSeg LGSS
> Codebase for CVPR2020 A Local-to-Global Approach to Multi-modal Movie Scene Segmentation

![demo image](images/pipeline.png)

## Introduction
From a video to segmented scenes. Basically, two steps are needed, including holistic features extraction and temporal scene segmentation.

A single-stage temporal scene segmentation is also provided in the [demo](docs/GETTING_STARTED.md#demo). This is going to be an easy-to-use tool for plot/story understanding with scene as a semantic unit.
Currently, it only supports image input.

从视频到分段场景。 基本上，需要两个步骤，包括整体特征提取和时间场景分割。

[演示](docs/GETTING_STARTED.md#demo) 中还提供了单阶段时间场景分割。 
这将成为一个易于使用的工具，用于以场景作为语义单元来理解情节/故事。
目前仅支持图片输入。

😬 The scene segmentation dataset is prompted to **[MovieNet](https://movienet.github.io/)** project with 318 movies together with a easy-to-use toolkit. It is encouraged to use in the future. 
😬 场景分割数据集提示 **[MovieNet](https://movienet.github.io/)** 项目，包含 318 部电影以及易于使用的工具包。 鼓励将来使用。

## Features
- Basic video processing tools are provided including [shot detection](pre/ShotDetection) and its parallel version.
- Holistic semantic video feature extractors including place, audio, human, action, speech are planned to be included if you wish and leave a looking forward message in the issue. Place and audio are supported now in the ``pre``. Full version is located at [movienet-tools](https://github.com/movienet/movienet-tools).
- All-in-one scene segmentation tool with all multi-modal multi-semantic elements.

- 提供基本的视频处理工具，包括[镜头检测](pre/ShotDetection)及其并行版本。
- 如果您愿意并在本期中留下期待的信息，计划包括包括地点、音频、人物、动作、语音在内的整体语义视频特征提取器。 现在“pre”中支持地点和音频。 完整版本位于[movienet-tools](https://github.com/movienet/movienet-tools)。
- 具有所有多模态多语义元素的一体化场景分割工具。

## Notice 
😅 Since some enthusiastic researchers are requesting the codes but we plan to organize the codebase in an easy-to-use fashion, e.g. [movienet-tools]((https://github.com/movienet/movienet-tools)), we release an on-going version here.
😅 由于一些热情的研究人员正在索取代码，但我们计划以易于使用的方式组织代码库，例如 [movienet-tools]((https://github.com/movienet/movienet-tools))，我们在这里发布了一个持续版本。

## Installation
Please refer to [INSTALL.md](docs/INSTALL.md) for installation and dataset preparation. Pretrained models and dataset are also explanined here.
安装和数据集准备请参考[INSTALL.md](docs/INSTALL.md)。 
这里还解释了预训练模型和数据集。

## Get Started
🥳 Please see [GETTING_STARTED.md](docs/GETTING_STARTED.md) for the basic usage.
🥳 基本用法请参见 [GETTING_STARTED.md](docs/GETTING_STARTED.md)。

## Citation
```
@inproceedings{rao2020local,
title={A Local-to-Global Approach to Multi-modal Movie Scene Segmentation},
author={Rao, Anyi and Xu, Linning and Xiong, Yu and Xu, Guodong and Huang, Qingqiu and Zhou, Bolei and Lin, Dahua},
booktitle={IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
year={2020}
}
```
