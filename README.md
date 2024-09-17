conda create -n NestedUnetTorch python=3.6

conda activate NestedUnetTorch

pip install simpleitk

pip install opencv-python==3.4.2.16

pip install scipy

pip install scikit-learn==0.20

pip install scikit-image

conda  install numpy  mkl cffi

conda install  torchvision  -c pytorch

conda install Pillow=6.1

conda install tqdm

conda install pandas

这里提供一个数据集，Unet++官方提供的
1. Download dataset from [here](https://www.kaggle.com/c/data-science-bowl-2018/data) to inputs/ and unzip. The file structure is the following:
```
inputs
└── <yourdataname>
 ├── images
     └── 00ae65...
 └── masks
     └── 00ae65...            
    ...
```


## Results
### DSB2018 (96x96)

Here is the results on DSB2018 dataset (96x96) with LovaszHingeLoss.

| Model                           |   IoU   |  Loss   |
|:------------------------------- |:-------:|:-------:|
| U-Net                           |  0.839  |  0.365  |
| Nested U-Net                    |  0.842  |**0.354**|
| Nested U-Net w/ Deepsupervision |**0.843**|  0.362  |



运行代码：
python train.py --dataset <dataset name> --arch NestedUNet --image-ext png --mask-ext png

根据命令行函数自己加参数就行