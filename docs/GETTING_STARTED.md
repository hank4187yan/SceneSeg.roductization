## Getting Started
## 实操指南
### Running
### 运行

```sh
cd lgss
python run.py config/xxx.py 
```

```run.py``` is the main process, which is encapsulated and controlled by ```config``` files.
Every running process creates a run folder containing experiments logs. 
And we prepare a script ```gen_csv.py``` to automaticly generate a csv file with desired setting and results records.
```run.py```是运行的主程序，它封装了```config```文件。
每一个运行过程都会创建一个实验文件夹，其中包含实验日志。
我们准备了一个脚本```gen_csv.py```来自动生成一个包含所需设置和结果记录的csv文件。

#### Test with pretrained models
#### 测试预训练模型
Please set up the config file in ```run``` folders and set ``trainFlag`` as ``False`` and ``testFlag`` as ``True``.
 修改```run```文件夹中的配置文件，将
 ``trainFlag``设置为``False``，
 ``testFlag``设置为``True``。

```sh
python run.py ../run/xxx/xxx.py 
 ```

This will automatically load the best model in the ``experiment_name`` folder.
If you wish to use a specific model, please use ``resume`` to include the model path.
它会自动加载``experiment_name``文件夹中的最佳模型。
如果你希望使用特定的模型，请使用``resume``包含模型路径。

#### Use different semantic elements
Modify the config file set dataset name as ``all`` and change the ``mode`` according to the preference
修改配置文件，将数据集名称设置为``all``，并根据偏好更改``mode``。
```python
dataset = dict(
    name = "all",
    mode=['place','cast','act','aud'],
)
 ```


### Preprocessing
#### 预处理
It is able to follow the following codes to process the data. Remember to read the ``argparase`` to choose an ideal setting.
它能够按照以下代码处理数据。记住阅读``argparase``以选择理想的设置。

```sh
cd pre
python ShotDetect/shotdetect.py # Cut shot 
python place/extrac_feat.py     # Extract place feature
python audio/extrac_feat.py     # Extract audio feature
 ```

And the full feature extraction is updated in [movienet-tools](https://github.com/movienet/movienet-tools)
并且完整的特征提取在[movienet-tools](https://github.com/movienet/movienet-tools)中更新

### Demo
#### 演示
#### Preparation
#### 准备
- [pytube](https://github.com/nficano/pytube) is to download YouTube video. Install with ```pip install pytube3 --upgrade```
- FFMPEG is to cut scene video and it is usually installed by your OS
- [pytube](https://github.com/nficano/pytube)是下载YouTube视频。使用```pip install pytube3 --upgrade```安装
- FFMPEG是切割场景视频，通常由操作系统安装

#### Run
#### 运行
```sh
cd pre
python demodownload.py ## Download a YouTube video with pytube
python ShotDetect/shotdetect.py --print_result --save_keyf --save_keyf_txt ## Cut shot 
cd ../lgss
python run.py config/demo.py ## Cut scene 
 ```

#### Notice
The video link in the ``pre/demodownload.py`` might be invalid as time goes, and it may change to your own.
视频链接在``pre/demodownload.py``中可能无效，因为时间流逝，它可能会改变到你的。

The demo code only use the image place feature for simplicity and casues inferior performance. It may change the threshold here to have a slight modification. The higher the threshold, the less scene it will generate. ``scene_dict, scene_list = pred2scene(cfg, threshold=0.8)``
演示代码只使用图像位置功能所特征进行简单性，并导致性能低下。
它可能在这里改变阈值以获得轻微的修改。阈值越高，它生成的场景就越少。``scene_dict, scene_list = pred2scene(cfg, threshold=0.8)

```pre/ShotDetect``` is developed based on [PySceneDetect](https://pyscenedetect.readthedocs.io/en/latest/). The shot detector is optimized to suit for movie.
``pre/ShotDetect``基于[PySceneDetect](https://pyscenedetect.readthedocs.io/en/latest/)开发。镜头检测器针对电影进行了优化。
**Parallel shot detection** 
**并行镜头检测**
``shotdetect_p.py`` is also included for future usage.
``shotdetect_p.py``也包含在内，它可能将来会用。