# 基于 Pytorch 的遥感图像分割

### 注：本项目核心算法代码为复现知乎@王振庆老师的代码。

## 1、绪论

- 基于不同地形地貌的高分辨率遥感影像资料，利用遥感影像智能解译技术识别提取土地覆盖和利用类型，实现生态资产盘点、土地利用动态监测、水环境监测与评估、耕地数量与监测等应用。结合现有的地物分类实际需求，参照地理国情监测、“三调”等既有地物分类标准，设计陆域土地覆盖与利用类目体系，包括：林地、草地、耕地、水域、道路、城镇建设用地、农村建设用地，工业用地、构筑物、裸地。
- 本实验旨在研究和评估基于Pytorch的遥感图像分割模型在语义分割任务中的性能。该模型采用了Unet++架构，以提高遥感图像分割的精度和效果。此外，项目还提供了两种不同的损失函数供用户选择，包括SoftCrossEntropyLoss+DiceLoss和SoftCrossEntropyLoss+LovaszLoss，以探究不同损失函数对分割结果的影响。

## 2、代码描述

- count_classes.py：统计数据中每个类的像素占比情况。
- data_process.py：数据预处理，分割训练集和测试集。
- train.py：是项目的主要代码文件，其中包含了模型的训练过程。用户可以在这个文件中设置训练参数，如 epoch 数、batch size、优化器等。通过运行 train.py 文件，可以启动训练过程，并观察模型在训练集上的学习和调整过程。
- 损失函数：项目提供了两种损失函数供用户选择，分别是 SoftCrossEntropyLoss+DiceLoss 和 SoftCrossEntropyLoss+LovaszLoss。这两种损失函数都是用于优化模型的，可以根据实际情况选择使用哪一种。在训练过程中，损失函数将用于计算模型预测结果与真实标签之间的差异，以引导模型学习和调整。
- 模型微调：项目还提供了模型微调的功能，用户可以通过运行 fine_tune 函数来进行模型微调。在 fine_tune 函数中，用户可以指定微调的参数和目标，例如选择微调的层、微调的学习率等。通过模型微调，可以进一步优化模型在特定数据集上的性能，以适应特定的遥感图像分割任务。

## 3、项目讲解视频
地址：【CV项目展示视频-基于Pytroch和Unet的遥感图像分割】 https://www.bilibili.com/video/BV1KV411g77S/?share_source=copy_web&vd_source=39163189a6d6cd6f57b8a4017d3df50c
