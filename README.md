# Hi, I'm Zepher · 胡左轩
> **视觉感知 × 边缘部署** —— 让模型在真实设备上跑得起来、跑得更快、跑得稳。
控制科学与工程硕士（2027 届），湖南科技大学，研究方向为无人机视角下的多模态小目标检测。
本科毕业于南京工程学院自动化专业。
我不是只做"训练完就交差"的算法，我关心模型从 PyTorch 到一块真实板子的完整链路：
算子能不能转过去、内存拷不拷贝、几路流水线能不打架、掉电之后能不能恢复。
---
## 我关注的问题
- **模型转换**：PyTorch → ONNX → RKNN / TensorRT，算子不兼容怎么等价改写
- **端侧推理**：RK3588 / Jetson AGX Xavier 上的多线程流水线、背压、保序与异常退出
- **异构数据通路**：DMA-BUF、RGA、V4L2、MPP，减少 CPU 侧的复制与计算
- **视觉算法**：小目标检测、RGB-T 多模态融合、单目标跟踪
---
## 代表项目
### 🔧 [RT-DETR on RK3588](https://github.com/zepher-kk/rt-detr-rk3588-deploy)
面向 VisDrone 无人机小目标检测的端侧部署。解决 RKNN 对 `GridSample`、高维 `Linear/MatMul`
的算子兼容问题，并用 C++ 三级异步流水线把串行推理改成多帧跨阶段并行。
端到端吞吐 **2.6 fps → 16 fps**。
`RKNN` `C++` `多线程` `RGA` `DMA-BUF`
### 🧠 [GroundingPI on RK3588](https://github.com/zepher-kk/groundingpi-rk3588)
把视觉-语言模型搬上边缘设备：TinyViT + Qwen3-3B 蒸馏学生模型，在 RK3588 上完成
端侧部署。目标是让"看得懂"和"跑得动"同时成立。
`VLM` `蒸馏` `RKLLM` `端侧推理`
### 🎯 [UAV-DETR+](https://github.com/zepher-kk/UAV-DETRimp)
第一作者论文配套代码。用多尺度聚焦 + 小波/傅里叶频域增强 + 语义对齐，
提升无人机图像中的小目标检测性能。
`小目标检测` `频域增强` `Transformer`
---
## 论文
| 论文 | 身份 | 发表 |
|---|---|---|
| UAV-DETR+: More tiny pixels and frequency information help small object detection | 第一作者 | Journal of Electronic Imaging 34(5), 053032 |
| SiamMGT: 掩码引导的孪生网络目标跟踪 | 第三作者 | Journal of Electronic Imaging 35(1), 013007 |
| FGD-Det: RGB-红外多光谱目标检测 | 第二作者 | Under Review |
---
## 技术栈
```
语言      Python · C++ · C · SQL
框架      PyTorch · MMDetection · Ultralytics
部署      ONNX · TensorRT · RKNN · RKLLM
平台      RK3588 · Jetson AGX Xavier · 鲁班猫4
系统      Linux · OpenCV · 多线程 · ROS2
```
---
## 联系
- 📧 zepher3464549297@outlook.com
- 🐙 GitHub: [@zepher-kk](https://github.com/zepher-kk)
> 如果你在做一个"模型必须跑在端上"的项目，欢迎聊聊。
