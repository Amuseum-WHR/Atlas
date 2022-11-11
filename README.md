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
Follow this [website](https://blog.csdn.net/weixin_46632183/article/details/120553750) to install pymesh

## download dataset
+ First, create a folder named "data"
+ Second, revise the corresponding path in dataset/dataset_shapenet.py" and training/metro.py
+ Download these zips: [metro_files.zip](https://jbox.sjtu.edu.cn/l/41tOlR) and unzip in folder "data"
+ P.S. My computer cannot afford the memory requirements to cache all data, so I only cache one third of the total datas.If you are willing to cache the whole data for our team, you can delete the folder cache and revise line 121 and line 123 in python file "dataset/dataset_shapenet.py". Just delete the part of "if count == 3" and run "测试用.ipynb", program will recache the entire dataset. 

## run
"测试用.ipynb" is a file to test code. You can change opt or model, start training and check loss info in the folder "log".

If you want to add log information, use 

```python
message = # your message
with open(self.log_name, "a") as log_file: # log_name is an attribute of class Trainer
      log_file.write('%s\n' % message)
```

If you want to save results, please save in the corresponding log path (check opt.log_path)
