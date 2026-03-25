# Convolution Visualizer Lab

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

[English](#english) | [中文](#chinese)

---

<a name="english"></a>

An interactive web-based convolution kernel simulator for image processing education and experimentation. Visualize how 3×3 convolution kernels transform images in real-time, with pixel-by-pixel animation demonstrating the mathematical operations.

### ✨ Features

- **Custom 3×3 Kernel Editor**: Input any floating-point values to create your own filters
- **10 Built-in Presets**: Identity, Sobel X/Y, Laplacian, Sharpen, Gaussian, Box Blur, Emboss, Outline
- **Real-time Processing**: Apply kernels instantly to uploaded images
- **Demo Mode**: Step-by-step pixel animation showing:
  - Input 3×3 pixel patch visualization
  - Kernel overlay with weights
  - Per-channel (RGB) convolution calculations
  - Final output pixel generation
- **Additional Filters**: Grayscale, Invert (non-convolution operations)
- **Export**: Download processed results as PNG

### 🚀 Quick Start

1. Open `index.html` in any modern browser
2. Upload an image or click "Use Example"
3. Select a preset or edit the 3×3 kernel manually
4. Click **"Apply Current Kernel"** button
5. Toggle "Demo Mode" to visualize the calculation process

### 📐 Mathematical Formula
$$
Output(x,y) = \frac{\sum [ Input(x+i, y+j) × Kernel(i,j) ]}{Divisor} + Bias \\
where\  i,j ∈ {-1, 0, 1}
$$

### 🎮 Controls

| Control | Description |
|---------|-------------|
| Kernel Grid | 9 inputs for 3×3 convolution weights |
| Divisor | Normalization factor (typically sum of weights) |
| Bias | Brightness offset (use 128 for edge detection) |
| Animation Speed | Pixels processed per frame in demo mode |
| Apply Button | **Must click** to activate custom kernel values |

### 🖼️ Preset Kernels

| Name | Kernel | Divisor | Bias | Use Case |
|------|--------|---------|------|----------|
| Identity | `0 0 0 / 0 1 0 / 0 0 0` | 1 | 0 | No change |
| Sobel X | `-1 0 1 / -2 0 2 / -1 0 1` | 1 | 128 | Vertical edges |
| Gaussian | `1 2 1 / 2 4 2 / 1 2 1` | 16 | 0 | Smooth blur |
| Sharpen | `0 -1 0 / -1 5 -1 / 0 -1 0` | 1 | 0 | Enhance details |
| Emboss | `-2 -1 0 / -1 1 1 / 0 1 2` | 1 | 128 | 3D relief effect |

### 🛠️ Technical Details

- Pure client-side processing (no server required)
- Canvas API for image manipulation
- Clamp edge handling (edge pixels replicate border values)
- RGB channels processed independently
- Value clamping to [0, 255] range

### 🔧 Browser Compatibility

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## 🤝 Contributing

Bug reports and feature requests are welcome! Please open an issue to discuss changes.

## 📜 License

[MIT License](LICENSE) - Feel free to use for educational and commercial purposes.

## 🎓 Educational Use

This tool is designed for:
- **Computer Vision Courses**: Demonstrating convolution operations
- **Digital Image Processing**: Visualizing filter effects
- **Deep Learning Education**: Understanding CNN kernel mechanics
- **Self-study**: Interactive experimentation with image kernels

---

## 卷积可视化实验室
<a name="chinese"></a>

基于 Web 的交互式卷积核模拟器，用于图像处理教学与实验。实时可视化 3×3 卷积核如何变换图像，并通过逐像素动画演示数学运算过程。

### ✨ 功能特性

- **自定义 3×3 卷积核编辑器**：输入任意浮点数值创建专属滤波器
- **10 种内置预设**：恒等、Sobel X/Y、拉普拉斯、锐化、高斯、均值模糊、浮雕、轮廓
- **实时处理**：即时应用卷积核到上传的图片
- **演示模式**：逐步像素动画展示：
  - 输入 3×3 像素块可视化
  - 卷积核权重叠加显示
  - 分通道（RGB）卷积计算过程
  - 最终输出像素生成
- **附加滤镜**：灰度化、负片（非卷积操作）
- **导出功能**：下载处理结果为 PNG 格式

### 🚀 快速开始

1. 用现代浏览器打开 `index.html`
2. 上传图片或点击"使用示例图片"
3. 选择预设或手动编辑 3×3 卷积核
4. 点击 **"应用当前卷积核"** 按钮
5. 开启"演示模式"可视化计算过程

### 📐 数学公式
$$
输出(x,y) = \frac{\sum[ 输入(x+i, y+j) × 卷积核(i,j) ]}{除数} + 偏移 \\
其中\ i,j ∈ {-1, 0, 1}
$$

### 🎮 控制说明

| 控件 | 说明 |
|------|------|
| 卷积核网格 | 9 个输入框对应 3×3 卷积权重 |
| 除数 | 归一化因子（通常为权重和） |
| 偏移 | 亮度偏移量（边缘检测建议用 128） |
| 动画速度 | 演示模式下每帧处理的像素数 |
| 应用按钮 | **必须点击** 以激活自定义卷积核数值 |

### 🖼️ 预设卷积核

| 名称 | 卷积核 | 除数 | 偏移 | 用途 |
|------|--------|------|------|------|
| 恒等 | `0 0 0 / 0 1 0 / 0 0 0` | 1 | 0 | 无变化 |
| Sobel X | `-1 0 1 / -2 0 2 / -1 0 1` | 1 | 128 | 垂直边缘检测 |
| 高斯模糊 | `1 2 1 / 2 4 2 / 1 2 1` | 16 | 0 | 平滑模糊 |
| 锐化 | `0 -1 0 / -1 5 -1 / 0 -1 0` | 1 | 0 | 增强细节 |
| 浮雕 | `-2 -1 0 / -1 1 1 / 0 1 2` | 1 | 128 | 3D 浮雕效果 |

### 🛠️ 技术细节

- 纯客户端处理（无需服务器）
- Canvas API 进行图像操作
- Clamp 边界处理（边缘像素复制边界值）
- RGB 三通道独立处理
- 数值截断到 [0, 255] 范围

### 🔧 浏览器兼容性

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## 🤝 贡献
欢迎提交错误报告和功能建议！请先开启 issue 讨论变更。

## 📜 License / 许可证

[MIT License](LICENSE) - Feel free to use for educational and commercial purposes.


## 🎓 教学应用

本工具适用于：
- **计算机视觉课程**：演示卷积运算
- **数字图像处理**：可视化滤波器效果
- **深度学习教学**：理解 CNN 卷积核机制
- **自学**：与图像卷积核进行交互式实验
