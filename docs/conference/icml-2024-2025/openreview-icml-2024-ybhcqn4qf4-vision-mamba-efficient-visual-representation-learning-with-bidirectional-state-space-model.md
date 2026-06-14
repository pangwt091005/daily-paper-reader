---
title: "Vision Mamba: Efficient Visual Representation Learning with Bidirectional State Space Model"
title_zh: Vision Mamba：基于双向状态空间模型的高效视觉表示学习
authors: "Lianghui Zhu, Bencheng Liao, Qian Zhang, Xinlong Wang, Wenyu Liu, Xinggang Wang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=YbHCqn4qF4"
tags: ["query:nutritionk"]
score: 5.0
evidence: 利用双向Mamba模型的高效视觉骨干，适用于食品图像营养成分估计
tldr: 当前视觉骨干依赖自注意力机制，计算开销大。本文提出Vision Mamba，使用双向状态空间模型（Mamba）构建视觉骨干，通过位置嵌入和双向状态压缩实现高效视觉表示。在ImageNet等任务上达到与Transformer相当的性能，且推理速度更快。该骨干可直接用于食品图像特征提取，支持深度学习的膳食评估。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ybhcqn4qf4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ybhcqn4qf4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1753, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ybhcqn4qf4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 826, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ybhcqn4qf4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 822, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ybhcqn4qf4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1774, \"height\": 472, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 768, \"height\": 1119, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 1271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 840, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 788, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 714, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 961, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ybhcqn4qf4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1029, \"height\": 709, \"label\": \"Table\"}]"
motivation: 自注意力机制计算昂贵，需要更高效的视觉骨干。
method: 提出双向Mamba块（Vim）构建视觉骨干，引入位置嵌入和双向压缩。
result: 在图像分类等任务上性能与Transformer相当，但效率更高。
conclusion: 为食品图像营养预测提供了一个高效的视觉特征提取基础架构。
---

## Abstract
Recently the state space models (SSMs) with efficient hardware-aware designs, i.e., the Mamba deep learning model, have shown great potential for long sequence modeling. Meanwhile building efficient and generic vision backbones purely upon SSMs is an appealing direction. However, representing visual data is challenging for SSMs due to the position-sensitivity of visual data and the requirement of global context for visual understanding. In this paper, we show that the reliance on self-attention for visual representation learning is not necessary and propose a new generic vision backbone with bidirectional Mamba blocks (Vim), which marks the image sequences with position embeddings and compresses the visual representation with bidirectional state space models. On ImageNet classification, COCO object detection, and ADE20k semantic segmentation tasks, Vim achieves higher performance compared to well-established vision transformers like DeiT, while also demonstrating significantly improved computation & memory efficiency. For example, Vim is 2.8x faster than DeiT and saves 86.8% GPU memory when performing batch inference to extract features on images with a resolution of 1248x1248. The results demonstrate that Vim is capable of overcoming the computation & memory constraints on performing Transformer-style understanding for high-resolution images and it has great potential to be the next-generation backbone for vision foundation models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前视觉骨干（如 Vision Transformer）高度依赖自注意力机制，其计算复杂度随序列长度二次增长，在处理高分辨率图像时面临显著的速度和内存瓶颈。能否构建一种纯状态空间模型（SSM）的通用视觉骨干，在保持甚至提升性能的同时大幅提高效率？
- **整体含义**：论文通过引入双向 Mamba 块（Vim），证明了自注意力并非视觉表示学习的必要条件。Vim 以线性复杂度实现数据依赖的全局上下文建模，在图像分类、目标检测、语义分割等主流任务上达到或超越优化后的 DeiT，并在高分辨率下实现 2.8 倍加速和 86.8% 内存节省，为构建高效视觉基础模型提供了新方向。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将图像处理为 patch 序列，使用双向状态空间模型（SSM）代替自注意力，结合位置嵌入实现空间感知，并通过硬件感知优化实现高效训练与推理。
- **关键技术细节**：
  - **图像分块与嵌入**：将输入图像 \(t \in \mathbb{R}^{H \times W \times C}\) 分割为大小为 \(P \times P\) 的非重叠 patch，线性投影为 \(D\) 维向量，并添加可学习的位置嵌入 \(E_{\text{pos}}\)，同时引入一个 class token \(t_{\text{cls}}\) 用于分类。
  - **双向 Vim 块**：在每个 Vim 块中，对输入序列同时进行前向和后向处理。每条路径包含：1D卷积 + SiLU 激活 → 线性投影得到 \(B_o, C_o, \Delta_o\) → 离散化 \(A_o, B_o\) → 循环 SSM 计算 → 门控（乘以 SiLU(z)）→ 前后向结果相加 → 线性投影 + 残差连接（详细流程见 Algorithm 1）。
  - **位置嵌入**：在初始嵌入阶段加入位置编码，使 SSM 具备空间位置感知能力，这对密集预测任务至关重要。
  - **效率优化**：采用与 Mamba 相同的硬件感知策略：将小尺寸参数（\(\Delta, A, B, C\)）从 HBM 加载到 SRAM 执行 SSM 计算，减少 IO 开销；在后向传播中重计算中间状态以降低显存占用。
- **公式与复杂度**：SSM 计算复杂度为 \(3M(2D)N + M(2D)N\)（\(N\) 为固定 SSM 维度，默认 16），相对于自注意力的 \(4MD^2 + 2M^2D\)，对序列长度 \(M\) 呈线性。

## 3. 实验设计

- **使用的数据集**：
  - **分类**：ImageNet-1K（128 万训练图像，50K 验证图像，1000 类）。
  - **语义分割**：ADE20K（20K 训练，2K 验证，150 类）。
  - **目标检测与实例分割**：COCO 2017（118K 训练，5K 验证）。
- **基准与对比方法**：
  - **ConvNet 基线**：ResNet-18/50/101/152，ResNeXt-50，RegNetY-4GF。
  - **Transformer 基线**：ViT-B/16，ViT-L/16，DeiT-Ti/S/B。
  - **SSM 基线**：S4ND-ViT-B。
  - **层次化架构额外对比**：Swin-T/S/B，Focal Transformer，CVT，MetaFormer，GFNet 等（通过将 Swin 的窗口注意力替换为全局双向 SSM 得到 Hier-Vim 变体）。
- **实验框架**：
  - 分类：直接使用 Vim 编码器 + MLP 头。
  - 分割：UperNet。
  - 检测与实例分割：Cascade Mask R-CNN（遵循 ViTDet 设置，Vim 无需窗口注意力）。

## 4. 资源与算力

- 文中明确说明：ImageNet 分类训练在 **8 张 A800 GPU** 上完成，批次大小 1024，训练 300 epochs，使用 AdamW 优化器，余弦学习率调度，初始学习率 \(1\times10^{-3}\)，权重衰减 0.05，使用 EMA。
- 长序列微调：再训练 30 epochs，恒定学习率 \(10^{-5}\)，权重衰减 \(10^{-8}\)。
- 其他下游任务（分割、检测）的训练设置中未明确说明 GPU 数量，但推测同样基于 A800 集群。训练总时长未在文中给出。

## 5. 实验数量与充分性

- **实验数量**：
  - 分类：Vim-Ti/S/B 三个尺度的结果，对比 14 种以上不同骨干。
  - 长序列微调：三种尺度的微调后性能（Vim-Ti/S/B †）。
  - 语义分割：Vim-Ti/S 与 DeiT-Ti/S、ResNet 对比。
  - 目标检测与实例分割：Vim-Ti 与 DeiT-Ti 对比。
  - 效率对比：不同分辨率（512~1248）下的 FPS 和 GPU 内存曲线（纯骨干 + FPN 模式）。
  - 消融实验：
    - 双向 SSM 设计：5 种策略（None、Bidirectional Layer、Bidirectional SSM、双向块、双向 SSM+Conv1d），在 ImageNet 和 ADE20K 上用 Segmenter 评估。
    - 分类设计：5 种策略（Mean pool、Max pool、Head class token、Double class token、Middle class token）。
  - 层次化架构额外对比：Hier-Vim-T/S/B 与 Swin、Focal Transformer 等对比。
- **充分性与公平性**：
  - 实验覆盖了主要视觉任务，对比方法均为 strong baseline（DeiT、ResNet、Swin 等）。
  - 消融实验系统验证了双向设计、分类头的必要性。
  - 效率对比采用与 DeiT 完全相同的推理环境（batch inference），控制变量。
  - 公平性：检测任务中，Vim 无需 2D 先验（窗口注意力），而 DeiT 为了高分辨率使用了窗口注意力，这实际上对 Vim 更不利，但 Vim 仍胜出。
  - 不足之处：未在大规模数据集（如 ImageNet-21K）上预训练；未与最新的超大模型（如 ConvNeXt-XXL、SwinV2）对比；缺少视频或其他模态的验证。

## 6. 论文的主要结论与发现

- **主要结论**：Vim 作为纯 SSM 视觉骨干，在 ImageNet 分类上以相近参数量全面超越 DeiT（Vim-Ti 76.1% vs. DeiT-Ti 72.2%），在下游密集预测任务上同样更优（ADE20K 分割 Vim-Ti 41.0 mIoU vs. DeiT-Ti 39.2 mIoU；COCO 检测 Vim-Ti 45.7 AP vs. DeiT-Ti 44.4 AP）。
- **效率发现**：随着图像分辨率升高，Vim 的速度和内存优势急剧扩大（1248×1248 时 2.8× 加速、86.8% 内存节省），证明线性复杂度的实际收益。
- **消融发现**：双向 SSM + 双向 1D 卷积是最优配置；中间 class token 策略比首部 class token 更好（76.1% vs. 75.2%）。
- **核心启示**：自注意力并非视觉表示学习所必需，SSM 可作为下一代通用骨干的基础。

## 7. 优点

- **方法创新**：首次提出纯 SSM 的通用视觉骨干，打破 Transformer 垄断，开辟新路径。
- **双向设计巧妙**：同时捕获前向和后向上下文，弥补单向 Mamba 的不足，兼顾全局性和位置感知。
- **计算效率突出**：线性复杂度 + 硬件感知优化，使高分辨率端到端处理成为可能。
- **实验扎实**：覆盖分类、分割、检测三大任务，消融设计严谨，效率对比直观。
- **开源友好**：代码和模型已公开，可复现。

## 8. 不足与局限

- **实验覆盖**：未在大规模预训练（如 ImageNet-21K、JFT）上验证，也未测试视频、3D 等更复杂的视觉数据。Vim 目前仅在监督学习下训练，自监督预训练尚未探索。
- **消融局限性**：分类设计中的“中间 class token”在 ImageNet 上表现好（中心物体先验），但可能不适用于无中心先验的任务（如全景分割）。
- **对比范围**：与 DeiT 对比充分，但与 Swin/ConvNeXt 的全面对比仅限层次化变体（Hier-Vim），且 Hier-Vim 只替换窗口注意力，未探索更优的分层设计。
- **超大规模实验缺失**：未与 ViT-G、SwinV2-G 等十亿级模型对比，缺乏对 scaling law 的验证。
- **潜在偏差**：数据增强、训练细节与 DeiT 完全一致，但可能存在对图像尺寸、长宽比的隐含依赖（因 SSM 是单向序列模型，图像扫描顺序会影响表征）。
- **应用限制**：当前版本仅适用于图像，多模态（如 CLIP 风格）和长视频理解尚未验证，但论文已作为未来工作提及。

（完）
