## A Light Weight Model for Active Speaker Detection

This repository contains code and models for our [paper](https://ieeexplore.ieee.org/abstract/document/9746742) (Accepted by CVPR 2023):

> A Light Weight Model for Active Speaker Detection  
> Junhua Liao, Haihan Duan, Kanghui Feng, Wanbing Zhao, Yanbing Yang, Liangyin Chen


***
### Evaluate on AVA-Activespeaker dataset 

#### Data preparation
Use the following code to download and preprocess the AVA dataset.
```
python trainTalkNet.py --dataPathAVA AVADataPath --download 
```
The AVA dataset and the labels will be downloaded into `AVADataPath`.

#### Training
You can train the model on the AVA dataset by using:
```
python train.py --dataPathAVA AVADataPath
```
`exps/exps1/score.txt`: output score file, `exps/exp1/model/model_00xx.model`: trained model, `exps/exps1/val_res.csv`: prediction for val set.

#### Testing
Download our model weight ([ICASSP_Model.pth.tar](https://drive.google.com/file/d/1nJLdf1hqvx22LhD_uDOT5O0JeDmapSqN/view?usp=sharing)) and place it in the `weight` folder. It performs `mAP: 94.1` in the validation set. You can check it by using: 
```
python train.py --dataPathAVA AVADataPath --evaluation
```


***
### Evaluate on Columbia ASD dataset

#### Testing
Download the model weight ([ICASSP_Model.pth.tar](https://drive.google.com/file/d/1nJLdf1hqvx22LhD_uDOT5O0JeDmapSqN/view?usp=sharing)) we trained on the AVA dataset and place it in the `weight` folder. You can check it by using: 
```
python Columbia_test.py --evalCol --colSavePath colDataPath
```
The Columnbia ASD dataset and the labels will be downloaded into `colDataPath`. Finally you can get the following F1 result.
| Name |  Bell  |  Boll  |  Lieb  |  Long  |  Sick  |  Avg.  |
|----- | ------ | ------ | ------ | ------ | ------ | ------ |
|  F1  |  82.7% |  75.7% |  87.0% |  74.5% |  85.4% |  81.1% |


***
### Citation

Please cite our paper if you use this code or model. 

```
@inproceedings{liao2023light,
  title={A Light Weight Model for Active Speaker Detection},
  author={Liao, Junhua and Duan, Haihan and Feng, Kanghui and Zhao, Wanbing and Yang, Yanbing and Chen, Liangyin},
  booktitle={IEEE Conference on Computer Vision and Pattern Recognition},
  year={2023},
  organization={IEEE}
}
```

***
### Acknowledgments

