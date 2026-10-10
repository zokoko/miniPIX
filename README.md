# miniPIX

![miniPIX](assets/minipix-banner.webp)

在浏览器里训练一个会画像素的神经网络。单个 HTML 文件、零依赖、不联网，双击 `miniPIX.html` 即可开始。

- **生成** — 输入 Prompt，轻量自回归像素 Transformer（单层单头、dModel 32）以 4×4 patch 逐个生成原生 100×100 像素图，支持风格条件、采样温度与 Pico-8 / NES / 灰度调色板后处理。
- **训练** — 100 张内置像素素材，也可上传自己的图像—文本配对样本；next-token 交叉熵 + 前景加权，完整反向传播与 Adam 更新，实时损失曲线和训练日志。
- **导出** — 权重 `minipix_weights.json`、数据集 `minipix_training_dataset.json`、`minipix_100x100.png`、`palette.json`、`scene.json`，以及打包了训练样本原始 RGBA 与训练历史的完整项目文件 `.minipixproject`；场景数据可输出通用 JSON / Three.js / Phaser / Godot / Unity 格式。

模型容量和数据量都很有限：生成是「真实权重采样 + 有标注的素材先验引导」，不是扩散模型，页面里的训练日志和说明同样标注了这条边界。
