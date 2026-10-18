# Apiginchaosr.github.io

个人学习笔记站点 —— 深度学习 / IC 设计。

## 内容

| 路径 | 说明 |
| --- | --- |
| `index.html` | 首页：身份信息、学习轨迹 |
| `deep-learning/01-mlp.html` | 第 01 章：用 MLP 识别手写数字，含 7 个可交互小节 |
| `deep-learning/02-gradient-descent.html` | 第 02 章：梯度下降，含 8 个可交互小节 |

## 技术

纯手写 HTML + CSS + Canvas，无框架、无构建、零外部依赖，可直接离线打开。

页面里的手写数字不是图片，是运行时用 Canvas 渲染字体、取墨迹包围盒、缩放到 20×20 内框居中，再做面积平均下采样得到的 28×28 灰度矩阵（复刻 MNIST 预处理）。

演示网络不训练：隐藏层用固定随机权重真算 ReLU 激活，输出层用输入与 10 个数字模板的方向余弦得到 logits，因此能在浏览器里毫秒级给出合理预测。

## 本地预览

```bash
python -m http.server 8000
# 打开 http://127.0.0.1:8000
```

---

© 2026 Apiginchaosr
