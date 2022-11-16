# Atlas

For the CV course Final project

## environment requirements (Linux recommanded)
+ python 3.7
+ cuda 11.3
+ pytorch 1.12.1
+ torchvision 0.13.1
+ pymesh
+ other missing modules you can use 'pip install xxx' to install

## install pymesh
Follow this [website](https://blog.csdn.net/weixin_46632183/article/details/120553750) to install pymesh.

## download dataset
+ First, create a folder named "data".
+ Second, revise the corresponding path in dataset/dataset_shapenet.py" and training/metro.py
+ Download these zips: [ShapeNetV1Renderings.zip](https://jbox.sjtu.edu.cn/l/l1dfYe) [ShapeNetV1PointCloud.zip](https://jbox.sjtu.edu.cn/l/01AwwD) [metro_files.zip](https://jbox.sjtu.edu.cn/l/41tOlR) [cache.zip](https://jbox.sjtu.edu.cn/l/b1d0PR) and unzip in folder "data".
+ P.S. My computer cannot afford the memory requirements to cache all data, so I only cache one third of the total datas.If you are willing to cache the whole data for our team, you can delete the folder cache and revise line 121 and line 123 in python file "dataset/dataset_shapenet.py". Just delete the part of "if count == 3" and run "For_Test.ipynb", program will recache the entire dataset. 

## run
"For_Test.ipynb" is a file to test code. You can change opt or model, start training and check loss info in the folder "log".

If you want to add log information, use 

```python
message = # your message
with open(self.log_name, "a") as log_file: # log_name is an attribute of class Trainer
      log_file.write('%s\n' % message)
```

If you want to save results, please save in the corresponding log path (check opt.log_path).





# TODO

- [ ] 接口实现 example 

    ```python
    from argparse import ArgumentParser
    def get_args():
        parser = ArgumentParser()
    
        parser.add_argument(
            "--n_epochs", default=41, type=int, help="the number of epochs to run."
        )
        parser.add_argument(
            "--lr", default = 0.0001, type = float, help="learning rate."
        )
    
        return parser.parse_args()
    
    
    self.__init__(self, opt)
    ```

- [ ] Pipeline

    - [ ] 梯度回传路径？
    
    - [ ] Loss 构成？
        
    - [ ] How to Modify the Mesh's Output with the ODN outputs?
        
        - [ ] 
        
- [ ] *Layout Estimation Net* 

    - [ ] 图形学相关知识？

    - [ ] output features ?

- [ ] 数据怎么处理！？

- [ ] 数据集处理、接口 dataset.load 适配后续feature extraction

    - [ ] 弄明白 data label 比如说 data是image， label是空间坐标
    - [ ] Pix 3D 在下载 
    - [ ] SUN RGB-D ？ 

- [ ] 

- [ ] Object Detection Network  尽早实现一下
    - [ ]  Attention Sum 注意一下是怎么实现
    
- [ ] 提出 IDAES

- [ ] Mesh Generation Net 

    - [ ] 除理大小不同的input image
    - [ ] 不同dimension的图片 如何用一个网络做encoding
    - [ ] AtlasNet 边缘检测 、 边缘强化 **实现** （用 某种 net 实现）？ 能否用传统CV实现？

