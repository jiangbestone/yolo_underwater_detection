## 比赛信息
- 比赛题目：水下光学目标检测智能算法赛项
- 比赛链接：https://www.heywhale.com/home/competition/605ab78821e3f6003b56a7d8

## 文件说明
- code : 存放所有相关代码的文件夹[YOLOV5]

        - data :训练数据路径设置 coco128.yaml中设置训练数据路径
        - models ：网络相关的代码文件夹
		- convertTrainLabel.py：将官方的数据集转换成yolo数据的格式
		- train.py :  训练代码， 运行该函数进行模型的训练，可以得到模型
        - detect.py : 预测代码
        - test.py :测试模型代码
        - test.sh : 预测测试集，生成结果的脚本   sh test.sh
        - train.sh : 训练脚本  sh trian.sh 
 
    
预训练文件下载链接：链接：https://pan.baidu.com/s/1Y7BY8DsN0HufsYvw6zmxDQ 
提取码：vsiz 


## 操作说明
- step1 : 将官方训练数据集解压后放入tcdata 文件夹
- step2 : 将预训练best.pt模型文件放入model_data文件夹
- step3 : 训练运行  sh train.sh  
    - train.sh 有两步
        -python convertTrainLabel.py
        -python train.py
- step4 : 生成结果 sh run.sh

## 思路说明
- 本方案采用了yolov5作为baseline



##改进思路
- 数据扩增：训练样本扩增随机竖直/水平翻折，色彩空间增强，使缺陷样本均匀
- 自适应anchor策略
- 适当减少回归框损失的权重
- 多尺度训练
- 空洞卷积替换FPN最后一层
- FPN改进尝试：NAS-FPN、AC-PFN
- 测试增强：对测试图片翻折旋转，然后将多个图片预测，结果融合
