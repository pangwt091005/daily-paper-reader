---
title: Improving fine-grained understanding in image-text pre-training
title_zh: 改进图像-文本预训练中的细粒度理解
authors: "Ioana Bica, Anastasija Ilic, Matthias Bauer, Goker Erdogan, Matko Bošnjak, Christos Kaplanis, Alexey A. Gritsenko, Matthias Minderer, Charles Blundell, Razvan Pascanu, Jovana Mitrovic"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=5nxIRQ8GNa"
tags: ["query:nutritionk"]
score: 6.0
evidence: 细粒度多模态图文表示学习方法
tldr: 现有图文预训练模型如CLIP在细粒度理解上存在不足，SPARC通过为每个文本token学习图像块的分组，并用稀疏相似度度量计算语言分组视觉嵌入，实现更精细的对比学习。该方法无需负样本，在多个视觉语言任务上表现出色，可迁移至食品图像营养分析等细粒度识别场景。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 874, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1733, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 744, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1608, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1412, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-5nxirq8gna/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1044, \"height\": 1411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1747, \"height\": 866, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 654, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 905, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1562, \"height\": 814, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1563, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1529, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1530, \"height\": 914, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-5nxirq8gna/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1734, \"height\": 420, \"label\": \"Table\"}]"
motivation: 现有图文预训练模型在细粒度视觉理解上有限，难以捕捉图像块与文本词之间的精细对应。
method: 提出SPARC方法，通过稀疏相似度学习每个文本token对应的图像块分组，并计算语言分组视觉嵌入进行对比学习。
result: 在多个基准上超越CLIP和SigLIP，提升了零样本分类和检索性能。
conclusion: SPARC提供了更精细的图文对齐方法，可应用于食品营养预测等需要细粒度理解的场景。
---

## Abstract
We introduce SPARse fine-grained Contrastive alignment (SPARC), a simple method for pretraining more fine-grained multimodal representations from image-text pairs. Given that multiple image patches often correspond to single words, we propose to learn a grouping of image patches for every token in the caption. To achieve this, we use a sparse similarity metric between image patches and language tokens and compute for each token a language-grouped vision embedding as the weighted average of patches. The token and language-grouped vision embeddings are then contrasted through a fine-grained sequence-wise loss that only depends on individual samples and does not require other batch samples as negatives, i.e., more detailed information is encoded in a computationally inexpensive way. SPARC combines this fine-grained loss with a contrastive loss between global image and text embeddings to learn representations that simultaneously encode global and local information. We thoroughly evaluate SPARC and show improved performance over competing approaches both on image-level tasks relying on coarse-grained information, e.g. classification, as well as region-level tasks relying on fine-grained information, e.g., retrieval, object detection, segmentation while also improving model faithfulness and captioning in foundational vision-language models.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的图像-文本预训练方法（如 CLIP、ALIGN）通过全局对比学习取得了优异的粗粒度表现（如图像分类、粗粒度检索），但在需要细粒度理解的任务（如目标检测、语义分割、对象计数、空间关系理解）上表现不佳。这些模型容易丢弃与全局匹配无关的局部细节信息，导致细粒度的定位能力弱。
- **研究背景**：已有一些工作尝试通过引入图像块与文本词之间的局部损失来学习细粒度对应关系，如 FILIP、GLoRIA、MGCA、PACL 等。但这些方法存在以下一个或多个问题：
  - 计算和内存开销大（需要计算全批次所有块与所有 token 的相似度）；
  - 使用 softmax 计算注意力权重导致“赢者通吃”的 one-to-one 映射，不符合实际中一个词对应多个图像块的情况；
  - 需要依赖预训练模型（如冻结 CLIP）来启动训练；
  - 训练不稳定（如 FILIP）。
- **本文目标**：提出 SPARC（Sparse Fine-grained Contrastive Alignment），一种简单、高效的方法，在图文预训练中同时学习全局和局部细粒度表示，不需要额外负样本，且能自然扩展到大批量训练。

## 2. 方法论

- **核心思想**：  
  对于每个图像-文本对，学习每个文本 token 对应的图像块分组（多个块对应一个词），从而构造“语言分组的视觉嵌入”（language-grouped vision embedding）。然后将这些分组嵌入与对应 token 嵌入进行序列级对比学习，结合全局对比损失，同时编码粗粒度和细粒度信息。

- **关键技术细节**：
  - **全局对齐损失**：与 CLIP 相同的标准批次级对比损失，最大化匹配图像-文本对的全局嵌入相似度，最小化不匹配对的相似度。
  - **细粒度对齐损失**（核心创新）：
    1. 对一个样本内的所有图像块嵌入和文本 token 嵌入计算余弦相似度矩阵 $S$，元素 $s_{lp}$ 表示第 $l$ 个 token 与第 $p$ 个 patch 的相似度。
    2. 对矩阵按列（patch 方向）进行 min-max 归一化到 [0,1]。
    3. **稀疏化**：设定阈值 $\sigma = 1/P$（$P$ 为 patch 数），将小于阈值的相似度置为 0，鼓励每个 token 只关注少数最相关的 patch。
    4. 将稀疏化后的相似度按行（token 方向）归一化得到对齐权重 $a_{lp}$。
    5. 对每个 token $l$，用权重 $a_{lp}$ 加权求和所有 patch 嵌入，得到语言分组视觉嵌入 $c_l$。
    6. 对每个图像-文本对，计算序列级对比损失：最大化每个 token 嵌入与其对应 $c_l$ 的相似度，最小化其与其他 $c_k$（$k\neq l$）的相似度。该损失**不依赖批次中的其他样本作为负样本**，仅使用序列内的负样本，计算和内存开销极低。
  - **总损失**：$\mathcal{L}_{\text{SPARC}} = \lambda_g \mathcal{L}_g + \lambda_f \mathcal{L}_f$，其中 $\lambda_g$ 和 $\lambda_f$ 为权重超参数。

- **算法流程说明**：
  1. 图像编码器输出 patch 嵌入，文本编码器输出 token 嵌入及全局嵌入。
  2. 计算全局对比损失。
  3. 对每个图像-文本对，计算稀疏相似度 → 对齐权重 → 语言分组视觉嵌入。
  4. 计算序列级局部对比损失。
  5. 加权求和得到总损失，反向传播更新参数。

## 3. 实验设计

- **数据集**：
  - **预训练数据集**：ALIGN（18 亿图文对）、JFT（40 亿图像，半自动标注类别）、LTIP（3.12 亿高质量图文对，含较丰富的描述）。采用多步训练策略，交替采样。
  - **下游任务数据集**：
    - 零样本分类：ImageNet、ImageNet-V2、ImageNet-R、ImageNet-C、ImageNet-A、ImageNet-Sketch。
    - 检索：Flickr30k、MSCOCO。
    - 细粒度定位：LVIS（目标检测）、PASCAL VOC / PASCAL Context（语义分割）。
    - 忠实度评估：MSCOCO（K-Precision 指标）。
    - 图像描述生成：MSCOCO、Flickr30k（在 Flamingo 风格 VLM 中评估）。

- **Benchmark**：与以下基线方法在相同预训练框架下进行公平对比：
  - CLIP、FILIP、PACL、GLoRIA、MGCA。所有方法均使用相同架构（ViT-B/32，ViT-B/16，ViT-L/14）和随机初始化，从头训练，不依赖预训练模型。
- **评估指标**：Top-1 准确率、Recall@1/5/10、mAP、mIoU、K-Precision、CIDEr。

## 4. 资源与算力

- 论文明确说明了：
  - 训练使用 TPU v3，256 个 TPU core。
  - ViT-B 模型训练 200k 步（约 32 亿数据点），ViT-L 模型训练 250k 步（约 41 亿数据点）。
  - 批量大小：16384（除 GLoRIA 因内存限制使用 4096）。
  - AdamW 优化器，cosine 学习率调度，线性 warm-up 2500 步。
- 未给出具体 GPU 型号（TPU），但提供了详细的 FLOPs 和内存消耗分析（表 12、图 4）：SPARC 相比 CLIP 仅增加约 0.55% 的计算量和内存，远低于 GLoRIA、FILIP 等方法。

## 5. 实验数量与充分性

- **实验组数**：论文报告了大量实验，涵盖了：
  - **图像分类**：7 个数据集（IN, IN-V2 三个变体，IN-R, IN-C, IN-A, IN-Sketch）的零样本分类。
  - **检索**：Flickr30k 和 MSCOCO 上的图像→文本和文本→图像检索。
  - **目标检测**：LVIS（all 和 rare）和 MSCOCO 上的 mAP。
  - **语义分割**：PASCAL VOC 和 PASCAL Context 上的 mIoU。
  - **忠实度**：MSCOCO 上的 K-Precision（全部词及名词+形容词）。
  - **图像描述生成**：MSCOCO 和 Flickr30k 上的 CIDEr 分数。
  - **消融实验**：去除稀疏性、替换 softmax 的影响。
  - **多对一映射分析**：统计注意力权重的相对差异。
  - **计算/内存对比**：不同批量大小下的 FLOPs 和峰值内存。
- **充分性与公平性**：
  - 所有基线在同一框架下重新实现，使用相同骨干网络、预训练数据、训练超参数。
  - 对于 FILIP 训练不稳定问题，进行了额外实验（CLIP+FILIP 组合）。
  - 提供了多次运行的均值和标准差（如目标检测实验 ran 3 times）。
  - 消融实验验证各组件贡献。
  - 实验覆盖率较高，既涵盖粗粒度任务也涵盖细粒度任务，结论可靠。

## 6. 主要结论与发现

- SPARC 在**零样本分类**（所有 ImageNet 变体）上持续超越 CLIP 及所有竞争方法，尤其在 ViT-B/32 上提升显著（+1.4% ImageNet top-1）。
- 在**跨模态检索**（Flickr30k, MSCOCO）上同样领先，Recall@1 显著提升。
- 在**细粒度定位任务**上：
  - 目标检测：在 LVIS rare 类上比 CLIP 提升 +3.1% AP，表明 SPARC 学到了更信息丰富的细粒度表示。
  - 语义分割：在 PASCAL VOC 上 mIoU 27.36（CLIP 23.02），提升 4.34 分；在 PASCAL Context 上也提升。
- **模型忠实度**：SPARC 的 top-1 检索结果与真实描述的重叠率更高，尤其是名词和形容词（K-P_na），减少了对未出现物体的幻觉。
- **VLM 骨干**：在 Flamingo 风格模型中替换 CLIP 骨干后，MSCOCO CIDEr 从 24.3 提升至 25.3，Flickr30k 从 12.9 提升至 13.6。
- 稀疏化和非 softmax 归一化均贡献重要：去除稀疏性导致性能下降，替换为 softmax 导致更大幅度下降，且 softmax 导致严重的 one-to-one 映射倾向（峰值权重差异大）。

## 7. 优点

- **高效性**：局部损失仅在单个样本的序列内进行对比，不依赖批次负样本，计算和内存开销极低（仅比 CLIP 多 0.55%），易于扩展到大批量。
- **避免 softmax 的缺陷**：SPARC 使用 min-max 归一化加硬阈值稀疏化，避免了 softmax 的 winner-takes-all 和梯度消失问题，实现了灵活的多对一映射。
- **联合学习粗细粒度**：结合全局损失和局部损失，同时保留全局判别能力和局部定位信息。
- **无需预训练模型**：所有组件从头训练，简化了训练流程，公平对比了不同目标的纯收益。
- **稳定性**：作者报告训练过程中未出现因稀疏化导致的数值不稳定问题，相比之下 FILIP 很容易出现 NaN。
- **实验设计严谨**：提供了与多个基线的公平对比、消融、计算-精度权衡分析、定性可视化。

## 8. 不足与局限

- **实验覆盖**：
  - 没有在更细粒度的理解任务（如 VQA v2、文本指代分割、视觉推理）上进行评估，尽管声称提升了细粒度理解，但仅展示了定位任务（检测、分割）和忠实度。
  - 未测试在域迁移（如医学图像、食品图像）上的泛化能力。
- **偏差风险**：
  - 预训练数据来自网络（ALIGN 等），可能存在分布偏差或有害内容，论文未讨论。
  - 细粒度对齐依赖于文本 caption 中描述的准确性，对于 caption 质量低或缺失描述的内容可能学习不佳。
- **应用限制**：
  - 稀疏阈值固定为 1/P，对于极端情况（如非常小/大的物体）可能需要自适应阈值，但论文未探索。
  - 虽然计算效率高，但局部损失仅关注同一 pair 内的 token 之间的关系，没有利用跨样本的语义对应关系（如 MGCA 中的原型对齐），可能丢失部分跨样本语义。
- **消融实验不够深入**：仅做了两种消融（无稀疏、softmax），没有探究阈值选取、损失权重 λf 敏感性、不同归一化方法等。
- **可重复性**：论文提供了伪代码，但未提供开源实现（截至发表时），具体训练细节（如多数据集采样策略）需进一步说明。

（完）
