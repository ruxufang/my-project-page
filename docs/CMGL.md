# Cross-Modal Guidance Learning for Zero-Shot Industrial Anomaly Detection
## 项目简介
针对工业场景零样本缺陷检测，提出跨模态引导学习框架，将PatchCore与CLIP多模态特征结合，使用Dempster证据理论做多分支特征融合，提升未知缺陷OOD泛化能力。

## 网络架构
![网络架构图](imgs/background.png)

## 实验结果
在MVTec-AD数据集上测试：

### 小标题

| Method | Dataset | Image-level AUROC | Image-level AP |
|--------|---------|-------------------|----------------|
| Ours(CMGL-PatchCoreFuse) | MVTec-AD | 0.8532 | 0.9553 |
Epoch [29/50] loss=0.6498 ev_loss=0.0073 time=0.7s
Epoch [30/50] loss=0.6482 ev_loss=0.0064 time=0.7s
Epoch [31/50] loss=0.6484 ev_loss=0.0075 time=0.7s
Epoch [32/50] loss=0.6480 ev_loss=0.0072 time=0.7s
Epoch [33/50] loss=0.6469 ev_loss=0.0068 time=0.7s
Epoch [34/50] loss=0.6464 ev_loss=0.0070 time=0.7s
Epoch [35/50] loss=0.6462 ev_loss=0.0073 time=0.7s
Epoch [36/50] loss=0.6450 ev_loss=0.0066 time=0.7s
Epoch [37/50] loss=0.6449 ev_loss=0.0068 time=0.7s
Epoch [38/50] loss=0.6438 ev_loss=0.0062 time=0.7s

## 可视化对比
![缺陷检测可视化](imgs/R-C.jpg)

## 方法要点
1. PatchCore：提取图像局部特征，构建特征记忆库
2. CLIP：跨模态图文引导，引入文本语义先验
3. D-S证据理论：多分支特征证据融合，提升零样本泛化

## 环境依赖
```bash
torch>=2.0
timm
openai-clip
