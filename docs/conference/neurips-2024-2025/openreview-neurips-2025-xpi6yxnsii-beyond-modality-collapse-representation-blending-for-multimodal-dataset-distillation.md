---
title: "Beyond Modality Collapse: Representation Blending for Multimodal Dataset Distillation"
title_zh: 超越模态坍塌：多模态数据集蒸馏中的表示混合
authors: "Xin Zhang, Ziruo Zhang, Jiawei Du, Zuozhu Liu, Joey Tianyi Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Xpi6YxNSiI"
tags: ["query:nutritionk"]
score: 5.0
evidence: 解决模态坍塌的多模态数据集蒸馏
tldr: 多模态数据集蒸馏中普遍存在模态坍塌问题：压缩导致表示过度集中、模态间分布差距扩大。本文首次揭示该问题源于蒸馏的过度压缩与对比监督之间的冲突，并提出RepBlend框架，通过表示混合策略削弱过强的跨模态监督。在多个图像-文本数据集上，RepBlend有效保持模态多样性，提升下游模型性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1086, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 660, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpi6yxnsii/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 510, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 669, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1362, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1314, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpi6yxnsii/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 625, \"height\": 348, \"label\": \"Table\"}]"
motivation: 现有蒸馏方法面临模态坍塌，压缩与对比监督冲突。
method: 提出RepBlend框架，通过表示混合来平衡压缩和跨模态对齐。
result: 在多个数据集上缓解模态坍塌，提升蒸馏后模型的表现。
conclusion: RepBlend为多模态数据集蒸馏提供了更鲁棒的方法，适用于图像-文本学习。
---

## Abstract
Multimodal Dataset Distillation (MDD) seeks to condense large-scale image-text datasets into compact surrogates while retaining their effectiveness for cross-modal learning. Despite recent progress, existing MDD approaches often suffer from ***Modality Collapse***, characterized by over-concentrated intra-modal representations and enlarged distributional gap across modalities. In this paper, at the first time, we identify this issue as stemming from a fundamental conflict between the over-compression behavior inherent in dataset distillation and the cross-modal supervision imposed by contrastive objectives. To alleviate modality collapse, we introduce **RepBlend**, a novel MDD framework that weakens overdominant cross-modal supervision via representation blending, thereby significantly enhancing intra-modal diversity. Additionally, we observe that current MDD methods impose asymmetric supervision across modalities, resulting in biased optimization. To address this, we propose symmetric projection trajectory matching, which synchronizes the optimization dynamics using modality-specific projection heads, thereby promoting balanced supervision and enhancing cross-modal alignment.
Experiments on Flickr-30K and MS-COCO show that RepBlend consistently outperforms prior state-of-the-art MDD methods, achieving significant gains in retrieval performance (e.g., +9.4 IR@10, +6.3 TR@10 under the 100-pair setting) and offering up to 6.7$\times$ distillation speedup.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

多模态数据集蒸馏（MDD）的目标是将大规模图像-文本数据集压缩为紧凑的合成数据集，同时保留其用于跨模态学习的有效性。然而，现有MDD方法普遍遭遇**模态坍塌（Modality Collapse）**，表现为：
- 模态内部表示过度集中，多样性丧失；
- 不同模态之间的嵌入分布差距显著扩大，跨模态对齐变差。

作者首次指出，模态坍塌的根源在于**数据集蒸馏本身的过度压缩特性**与**对比学习施加的跨模态监督**之间存在根本性冲突。蒸馏过程倾向于收敛到少量主导特征，而对比学习又进一步强化这种收敛，导致模态内坍缩。此外，现有MDD方法在图像和文本分支上施加了**不对称的监督信号**，图像分支更新信号远弱于文本分支，导致优化偏差。

## 2. 方法论：核心思想、技术细节与流程

### 核心思想
提出 **RepBlend** 框架，通过**表示混合（Representation Blending）** 削弱过强的跨模态监督，增强模态内多样性；同时引入**对称投影轨迹匹配（Symmetric Projection Trajectory Matching）** 平衡跨模态监督，提升对齐效果。

### 关键技术细节
1. **表示混合（RB）**：在表示空间中对不同合成实例的特征进行线性插值（类似MixUp但应用于特征层）。例如，对文本表示：
   \[
   \tilde{\omega}_m^{\text{blend}} = \text{Normalize}\left( f_{\text{textP}}((1-\varrho)\tilde{\omega}_m + \varrho\tilde{\omega}_i) \right)
   \]
   其中 \(\tilde{\omega}_i\) 为其他实例的表示，\(\varrho\) 控制混合强度。该方法可降低模态内相似性，同时避免引入随机噪声导致的跨模态间隙扩大。

2. **对称投影轨迹匹配（SM）**：在原有仅匹配文本投影头的基础上，新增图像投影头，并同时匹配两个投影头的优化轨迹。损失函数为：
   \[
   \min_{\tilde{x},\tilde{\omega},\tilde{y}} \frac{\|\varepsilon_{S,\text{imgP}}^{t+T} - \varepsilon_{D,\text{imgP}}^{t+M}\|_2^2 + \|\varepsilon_{S,\text{textP}}^{t+T} - \varepsilon_{D,\text{textP}}^{t+M}\|_2^2}{\|\varepsilon_{D,\text{imgP}}^{t} - \varepsilon_{D,\text{imgP}}^{t+M}\|_2^2 + \|\varepsilon_{D,\text{textP}}^{t} - \varepsilon_{D,\text{textP}}^{t+M}\|_2^2}
   \]
   其中图像编码器保持冻结，仅训练投影头。此举使图像侧更新幅度与文本侧更为同步，缩小模态间隙。

### 算法流程（文字描述）
1. 初始化合成数据集S为随机图像-文本对及one-hot标签。
2. 加载预训练的图像编码器和文本编码器并冻结；随机初始化图像和文本投影头。
3. 收集真实数据集D上的专家轨迹（投影头权重序列）。
4. 迭代优化S：
   - 从真实轨迹中采样起点和终点权重。
   - 在合成数据集S上，通过表示混合增强后的特征计算加权二元交叉熵损失（wBCE），更新投影头权重，得到T步合成轨迹。
   - 利用对称投影轨迹匹配目标优化合成数据（图像像素、文本嵌入、软标签）。

## 3. 实验设计

### 数据集与场景
- 主要实验：**Flickr-30K**（约31k图像）和 **MS-COCO**（约123k图像），每个图像对应5个标题。
- 扩展实验：**LLaVA-cc3m**（约334k对，用于大规模验证）；**AudioCaps**（音频-文本跨模态场景）。
- 零样本泛化：ImageNet-10分类（10类）、TextCaps检索（OCR相关）。

### Benchmark
- 对比方法：**Coreset选择**（Random、Herding、K-Center、Forgetting）和**数据集蒸馏**（MTT-VL、TESLA-VL、LoRS）。
- 评价指标：跨模态检索的Recall@K（IR@1/5/10 图像检索文本，TR@1/5/10 文本检索图像）。

### 对比方法
- **LoRS**（当前SOTA）、**MTT-VL**、**TESLA-VL** 等。

## 4. 资源与算力

- 使用 **2块 NVIDIA RTX 3090 GPU**（24GB）和 **1块 NVIDIA H100 GPU**（80GB）。
- 具体训练时长未在正文中给出，但报告中提到：
  - 缓冲区生成：每个轨迹从70分钟降至40分钟（1.75×加速）。
  - 蒸馏阶段：每迭代从11.5秒降至1.71秒（6.7×加速）。
  - 峰值GPU显存：从21.78GB降至10.17GB。
- 明确说明使用PyTorch，未提及具体训练或微调总时长。

## 5. 实验数量与充分性

### 实验组数
- **主实验结果**（表1、2）：Flickr-30K和MS-COCO上各三种蒸馏预算（100/200/500对），每种报告R@1/5/10，共约12组对比。
- **消融实验**（图5）：分别在100/200/500对下对比RB和SM的贡献，共6组。
- **跨架构泛化**（表4）：NFNet+BERT蒸馏的数据在ResNet/BERT和RegNet/BERT上测试，两种架构各一次。
- **跨模态泛化**（附录H）：AudioCaps实验。
- **零样本泛化**（表5）：ImageNet-10和TextCaps。
- **大规模模型实验**（表3）：LLaVA-cc3m和Dino-v2+BGE-1.5等，三种预算。

### 充分性评估
- **客观性**：所有主实验重复5次并报告均值±标准差；对比方法均使用开源实现或官方结果。
- **公平性**：所有蒸馏预算统一设置，包括为LoRS和RepBlend同样预留一对用于相似矩阵开销。
- **不足**：仅在两个主数据集上进行了完整对比；MS-COCO上蒸馏预算较低（最多500对，仅0.4%），对更高压缩比的验证尚可，但未探索更大预算（如1000对）。

## 6. 主要结论与发现

- RepBlend在所有蒸馏预算和数据集上显著优于现有SOTA，尤其在低数据场景（如Flickr-30K 100对）下，IR@10提升9.4个百分点，TR@10提升6.3个百分点。
- 表示混合有效降低模态内相似性并缩小模态间隙，且优于加入高斯噪声的方法。
- 对称投影轨迹匹配使图像侧和文本侧更新更均衡，进一步提升跨模态对齐。
- 蒸馏效率大幅提升（6.7×速度提升，显存减半），同时保持或提升性能。
- 零样本泛化能力同样优于LoRS。

## 7. 优点

1. **问题新颖性**：首次明确定义并理论分析多模态蒸馏中的“模态坍塌”现象，指出对比监督与蒸馏压缩的冲突。
2. **方法有效性**：表示混合简单且高效，无需额外参数，对称匹配仅增加少量投影头但显著提升平衡性。
3. **实验全面**：涵盖多种数据集（图像-文本、音频-文本）、多种架构（CNN、ViT、Transformer）、多种蒸馏预算，并附加零样本和跨架构测试。
4. **效率优势**：通过冻结编码器、仅训练投影头，大幅降低存储和计算成本，实际应用中更易落地。
5. **理论支撑**：给出了跨模态监督如何强化模态内相似性的梯度推导（式3），增强了说服力。
6. **代码开源**：提供GitHub仓库，便于复现与推广。

## 8. 不足与局限

1. **模态覆盖有限**：仅实验了图像-文本和音频-文本，未扩展到视频-文本、3D-文本等更复杂多模态场景。
2. **压缩比限制**：最大蒸馏预算仅为500对（MS-COCO 0.4%），更高压缩比（如10对、1对）下的表现未探索，泛化性待验证。
3. **跨实例交互不足**：作者自承当前方法仅进行成对建模，缺乏文本token与视觉对象间的细粒度对齐，也未建模样本间关系。
4. **消融实验细节缺失**：未提供混合系数ρ的敏感度分析，也未讨论不同混合策略（如随机vs.基于语义）的影响。
5. **零样本测试规模小**：ImageNet-10仅10类，代表性有限；TextCaps任务中绝对性能较低（IR@1=3.1%），实际应用价值待提升。
6. **重复性细节略少**：虽然提供了算法和超参数表，但未明确说明训练总轮数、学习率调度等关键训练细节，可能影响复现。

（完）
