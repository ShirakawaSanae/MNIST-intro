## Welcome to MNIST! 

本仓库旨在通过深度学习中的经典案例（手写数字识别），以最易于接受的单个代码文件的形式，向深度学习初学者展示神经网络和模型训练的工作过程。

请自行搜索深度学习的相关数学原理，例如卷积、归一化。推荐移步 [【3Blue1Brown】深度学习之神经网络的结构 Part 1 ver 2.0](https://www.bilibili.com/video/BV1bx411M7Zx/?spm_id_from=333.1387.homepage.video_card.click&vd_source=09d1bf2cbd84e8b3aa3357a436352b3a)

## from FNN to CNN

基于MNIST数据集实现了卷积神经网络手写数字识别

**数据集来源**：torch内置可下载

**用法**：在命令行/终端输入

```
    pip install torch torchvision torchaudio (无 CUDA support)
	(如果你的显卡支持CUDA，请访问https://developer.nvidia.com/cuda-toolkit获得对应版本的命令 )
	pip install matplotlib numpy
	python <程序名>
```

**程序结构**：

```
CNN-model.py
│── Net (卷积神经网络)
│   ├── __init__()  (初始化 CNN 结构)
│   ├── forward()  (前向传播)
│── Tester (测试模型)
│   ├── __init__()  (初始化测试器)
│   ├── evaluate()  (计算模型在测试集上的准确率)
│   ├── show_predictions()  (可视化预测结果,可调参)
│── Model (训练模型)
│   ├── __init__()  (初始化训练器)
│   ├── train()  (训练模型)
│   ├── plot_loss()  (绘制训练损失曲线)
│── __main__ (主程序入口)
│   ├── model = Model()  (创建模型实例)
│   ├── model.train()  (执行训练)
│   ├── model.plot_loss()  (绘制损失曲线)
│   ├── model.tester.show_predictions()  (展示预测结果)
```

**注：**

- CNN与FNN的对比可以参考 `fixed_FNN-model.py` 对比 `CNN-model.py`
- 在 `fixed_FNN-model.py` 的注释中展示了用 `torch.nn.sequential` 直接传入模型的写法
- 更多细节请阅读注释

    
### **MNIST 数据集**

MNIST（Modified National Institute of Standards and Technology）是一个用于手写数字识别的标准数据集，由 0 到 9 共 10 种类别的 28×28 灰度图像组成。该数据集包含 60,000 张训练图像和 10,000 张测试图像，广泛用于机器学习和深度学习的研究。由于其数据集规模适中且预处理简单，MNIST 经常被用于测试图像分类算法，是深度学习入门的理想数据集。

### **PyTorch**

PyTorch 是一个开源的深度学习框架，由 Facebook 开发，采用动态图计算机制，提供灵活的张量计算和自动求导功能，使其在深度学习任务中易于调试和优化。此外，PyTorch 具有强大的 GPU 加速能力，支持分布式训练，并且与 Python 生态系统兼容，便于与 NumPy、Scikit-learn 等库集成。

### **深度神经网络**

深度神经网络（DNN, Deep Neural Network）是一种由多层神经元组成的人工神经网络，通过模拟人脑神经元的连接方式来处理复杂任务。DNN 由**输入层、隐藏层和输出层**组成，其中隐藏层的增加使网络具有更强的特征提取和表达能力。
