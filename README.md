# Apiginchaosr.github.io

个人学习笔记站点 —— 深度学习 / IC 设计。

## 内容

| 路径 | 说明 |
| --- | --- |
| `index.html` | 首页：身份信息、学习轨迹 |
| `deep-learning/01-mlp.html` | 第 01 章：用 MLP 识别手写数字，含 7 个可交互小节 |
| `deep-learning/02-gradient-descent.html` | 第 02 章：梯度下降，含 8 个可交互小节 |
| `deep-learning/03-backprop.html` | 第 03 章：反向传播，含 8 个可交互小节 |
| `signals/01-convolution.html` | 信号与系统 01：卷积，含 4 个可交互小节 |
| `signals/02-fourier.html` | 信号与系统 02：傅里叶变换，含 3 个可交互小节 |
| `analog/01-miller-body.html` | 模拟集成电路 01：密勒效应与背栅效应，8 节，静态电路图 |

## 参考

深度学习部分的脉络参考 [3Blue1Brown](https://www.3blue1brown.com/topics/neural-networks) 的《深度学习》系列（共 4 集），章节页顶部都标了对应的集数：

| 集 | 原片 | B 站（官方双语） | 对应章节 |
| --- | --- | --- | --- |
| 1 | But what is a Neural Network? | [BV1bx411M7Zx](https://www.bilibili.com/video/BV1bx411M7Zx/) | 01 · MLP 识别手写数字 |
| 2 | Gradient descent, how neural networks learn | [BV1Ux411j7ri](https://www.bilibili.com/video/BV1Ux411j7ri/) | 02 · 梯度下降 |
| 3 | What is backpropagation really doing? | [BV16x411V7Qg](https://www.bilibili.com/video/BV16x411V7Qg/) 上篇 | 03 · 反向传播 |
| 4 | Backpropagation calculus | [BV16x411V7Qg](https://www.bilibili.com/video/BV16x411V7Qg/?p=2) 下篇 | 03 · 反向传播 |

B 站系列合集：<https://space.bilibili.com/88461692/channel/seriesdetail?sid=1528929>

信号与系统部分同样参考 3Blue1Brown 的两期可视化：

| 视频 | B 站 | 对应章节 |
| --- | --- | --- |
| 那么……什么是卷积？ | [BV1Vd4y1e7pj](https://www.bilibili.com/video/BV1Vd4y1e7pj/) | 卷积 |
| 形象展示傅里叶变换 | [BV1pW411J7s8](https://www.bilibili.com/video/BV1pW411J7s8/) | 傅里叶变换 |

模拟集成电路部分没有对应的视频，内容来自教材（Razavi《模拟 CMOS 集成电路设计》、Sedra/Smith《微电子电路》）的经典结论，数值按 0.18 μm 工艺自行代入核算。

站点不是原片的文字搬运：原片建立直觉的部分直接沿用，每一处数学都补上了能在浏览器里动手操作的版本。系列之外会继续写 CNN 与注意力机制。

## 技术

纯手写 HTML + CSS + Canvas + SVG，无框架、无构建、零外部依赖，可直接离线打开。

电路图不是截图也不是位图，是运行时用 JS 生成的 SVG：电阻、电容、MOS、地符号各自是一个函数，连线独立画，坐标手算对齐。所以放大、改主题、打印都不会糊。

页面里的手写数字不是图片，是运行时用 Canvas 渲染字体、取墨迹包围盒、缩放到 20×20 内框居中，再做面积平均下采样得到的 28×28 灰度矩阵（复刻 MNIST 预处理）。

演示网络不训练：隐藏层用固定随机权重真算 ReLU 激活，输出层用输入与 10 个数字模板的方向余弦得到 logits，因此能在浏览器里毫秒级给出合理预测。

## 本地预览

```bash
python -m http.server 8000
# 打开 http://127.0.0.1:8000
```

---

© 2026 Apiginchaosr
