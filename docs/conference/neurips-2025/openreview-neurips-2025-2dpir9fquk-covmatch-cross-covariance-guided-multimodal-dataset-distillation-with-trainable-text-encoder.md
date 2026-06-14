---
title: "CovMatch: Cross-Covariance Guided Multimodal Dataset Distillation with Trainable Text Encoder"
title_zh: CovMatch：基于交叉协方差引导的可训练文本编码器多模态数据集蒸馏
authors: "Yongmin Lee, Hye Won Chung"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2dpiR9fqUk"
tags: ["query:nutritionk"]
score: 4.0
evidence: 适用于食品图像-文本对的多模态数据集蒸馏方法
tldr: 现有数据集蒸馏方法在多模态对比学习中面临语义对齐瓶颈。本文提出CovMatch，通过交叉协方差对齐真实与合成特征，在保持可扩展性的同时提升多模态对齐效果。该方法可高效生成少量训练样本，为食品营养成分预测等任务提供支持。实验表明CovMatch在多个基准上取得领先结果，有望降低视觉语言模型在食品领域的数据需求。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 745, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1161, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 1198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 687, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1318, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 588, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 997, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1045, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1175, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1217, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1271, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1340, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 827, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 709, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1194, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 631, \"height\": 141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1423, \"height\": 821, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1458, \"height\": 849, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1454, \"height\": 1377, \"label\": \"Table\"}]"
motivation: 现有冻结文本编码器的多模态数据集蒸馏方法限制了语义对齐，成为性能瓶颈。
method: 提出CovMatch，引入交叉协方差对齐策略，联合优化图像编码器、文本编码器与投影层，实现高效多模态蒸馏。
result: 在多个多模态基准上，CovMatch显著优于现有蒸馏方法，且保持较低计算成本。
conclusion: CovMatch提供了一种可扩展的多模态蒸馏框架，可推广至食品图像营养分析等领域。
---

## Abstract
Multimodal dataset distillation aims to synthesize a small set of image-text pairs that enables efficient training of large-scale vision-language models. While dataset distillation has shown promise in unimodal tasks, extending it to multimodal contrastive learning presents key challenges: learning cross-modal alignment and managing the high computational cost of large encoders. Prior approaches address scalability by freezing the text encoder and update only the image encoder and text projection layer.  However, we find this severely limits semantic alignment and becomes a bottleneck for performance scaling.
We propose CovMatch, a scalable dataset distillation framework that aligns the cross-covariance of real and synthetic features while regularizing feature distributions within each modality. Unlike prior approaches, CovMatch enables joint optimization of both encoders, leading to stronger cross-modal alignment and improved performance. Evaluated on Flickr30K and COCO, CovMatch outperforms state-of-the-art multimodal distillation methods and achieves up to 6.8\% absolute gains in retrieval accuracy using only 500 synthetic pairs.

---

## 论文详细总结（自动生成）

# 论文《CovMatch》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：多模态数据集蒸馏旨在从海量图像-文本对中合成少量代表性样本，从而高效训练视觉-语言模型（如CLIP）。已有的单模态数据集蒸馏方法（如MTT）虽在图像分类中成功，但扩展到多模态对比学习面临两大挑战：**跨模态语义对齐**和**高计算成本**（因为编码器规模巨大，如NFNet:140MB、BERT:450MB）。
- **现有方法的不足**：前期工作（MTT-VL、LoRS）为缓解计算压力，通常冻结文本编码器，仅更新图像编码器和投影层。但本文发现这种策略**严重限制了语义对齐能力**，导致合成数据性能随规模增大而饱和甚至下降（例如LoRS在>1000对时不如随机选取的真实数据）。
- **核心问题**：如何在不牺牲可扩展性的前提下，实现图像与文本编码器的**联合优化**，从而提升跨模态对齐和蒸馏性能。
- **整体含义**：提出CovMatch，通过**交叉协方差匹配**框架，在不存储专家轨迹、无需展开内循环的条件下，实现端到端的双编码器联合蒸馏，达到了显著优于前人的检索准确率。

## 2. 方法论：核心思想、关键技术、算法流程
### 2.1 核心思想
- 将双层蒸馏优化（内循环在合成数据上训练模型，外循环在真实数据上评估并更新合成数据）**简化为闭式解形式**。
- 具体做法：每步蒸馏中**固定图像和文本编码器**，仅优化线性投影层。此时，内循环的对比学习损失可转化为**交叉协方差矩阵**的迹形式，并得到闭式最优解：$\hat{G}_v^\top \hat{G}_l = \frac{1}{\rho} C_S$，其中$C_S$为合成数据的交叉协方差矩阵。
- 因此外循环目标等价于**最大化真实交叉协方差与合成交叉协方差的迹**，即对齐两者。

### 2.2 关键技术细节
- **交叉协方差匹配损失**（公式11）：$L_{cov} = \|\rho \cdot C_T - C_S\|_F^2$，其中$\rho$为缩放超参数，$C_T$和$C_S$分别为真实和合成数据特征的交叉协方差矩阵（特征来自编码器输出，投影前）。
- **特征匹配正则化**（公式12）：为弥补交叉协方差低秩导致的约束不足，分别对图像和文本模态计算**投影后特征的均值差异**（最大均值差异MMD）：$L_{feat}^m = \| \frac{1}{|T|}\sum G_m f_m(x_i^m) - \frac{1}{|S|}\sum G_m f_m(\hat{x}_j^m) \|^2$。
- 总损失：$L_{CovMatch} = L_{cov} + \lambda (L_{feat}^v + L_{feat}^l)$。
- **在线模型更新**：每步蒸馏前，用真实数据的一批样本对编码器和投影层**进行一次梯度更新**，避免过拟合当前模型状态；每$T$步重置编码器为预训练权重并随机初始化投影层。

### 2.3 算法流程（文字描述）
1. **初始化**：从训练集中随机选取$N$对图像-文本作为初始合成数据集$S$；加载预训练图像/文本编码器，随机初始化投影层。
2. **迭代**（共$T$步或直至收敛）：
   - 从真实数据$T$中采样小批量$B_T$，从合成数据$S$中采样小批量$B_S$（若$N$较大则采样，否则全量）。
   - 计算$L_{CovMatch}$，并更新$S$（图像像素和文本嵌入）以最小化该损失（SGD，学习率1.0，动量0.5）。
   - 用$B_T$对模型（编码器+投影层）进行一次训练更新（标准对比学习）。
3. **周期性重置**：每50步重新初始化编码器为预训练权重、投影层随机。
4. **输出**：优化后的合成数据集$S$。
5. **评估阶段**：用$S$从头训练一个新模型（100 epochs），在测试集上评估图像→文本和文本→图像检索性能。

## 3. 实验设计
### 3.1 数据集与任务
- **Flickr30K**：约31K图像，每图5句话，采用Karpathy split（29K训练/1K验证/1K测试）。
- **COCO**：123K图像，同样5句话，split为113K/5K/5K。
- **评估任务**：图文跨模态检索，指标包括IR@1,5,10（文本→图像）和TR@1,5,10（图像→文本），以及平均准确率。

### 3.2 对比方法
- **Coreset选择**：Random（随机采样）、Herding、K-Center（均适应多模态）。
- **蒸馏方法**：MTT-VL（轨迹匹配，冻结文本编码器）、LoRS（低秩相似度挖掘，冻结文本编码器）。
- **其他扩展实验**：跨架构泛化（图像编码器换用NF-ResNet、NF-RegNet、ViT；文本编码器换用DistilBERT）；视频-文本检索（WebVid-10M子集）。

### 3.3 硬件与训练细节
- 图像编码器：NFNet L0（26.4M参数）；文本编码器：BERT-base（110M参数）；投影层维度2304（默认）。
- 合成数据规模：100、200、500对（分别占Flickr30K的0.3%、0.7%、1.7%；COCO的0.1%、0.2%、0.4%）。
- 蒸馏迭代：默认10,000次；500对时20,000次。
- 超参数：ρ在100对时为2，≥200对时为1；λ在100/200对时为0.1，500对时为0.5~0.6。
- 随机种子：每个实验5次重复，报告均值和标准差。

## 4. 资源与算力
- **GPU**：A100 80GB（单卡）。
- **存储**：CovMatch**无需存储专家轨迹**，存储需求为0GB；对比MTT（多模态）需120GB。
- **内存**：约15GB（与MTT单模态相当）；MTT多模态需71GB。
- **时间**：每迭代约1.2秒；蒸馏500对时约20,000次迭代，总时长约6.7小时（估计）；MTT多模态需132小时训练专家轨迹+19.2秒/迭代。
- **结论**：CovMatch在资源消耗上**极低**，显著优于需轨迹存储的长程匹配方法。

## 5. 实验数量与充分性
- **主要实验**：在Flickr30K和COCO上，分别对100、200、500合成对进行了评测，涵盖6个检索指标，并与5种基线对比（Random、Herding、K-Center、MTT-VL、LoRS）。结果均报告5次平均±标准差，充分展示稳定性。
- **消融实验**：共6组，包括：
   - 缩放因子ρ（图5a）
   - 特征匹配权重λ（图5b）
   - 在线更新策略（固定/用合成数据/用真实数据，图5c）
   - 批次大小（表10）
   - 投影维度与深度（表11、12）
   - 单模态蒸馏（表13）
- **拓展实验**：
   - 跨架构泛化（4种图像编码器×2种文本编码器，表3）
   - 视频-文本检索（WebVid子集，表6）
   - 冻结文本编码器的影响（表8、9）
- **充分性评估**：实验设计全面，覆盖了方法各个组件、不同数据规模、跨架构迁移及不同模态（视频）。对比基线均为官方或复现版本，保证公平。唯一不足是未在更大规模数据集（如CC12M）或更多蒸馏方法（如IDC、DATM等）上测试，但作为NeurIPS论文已足够。

## 6. 主要结论与发现
1. **联合优化文本编码器至关重要**：冻结文本编码器导致语义对齐瓶颈，合成数据性能难以随规模增加而提升（如图2）。CovMatch通过交叉协方差对齐实现了双编码器联合训练，性能显著超越冻结方案。
2. **交叉协方差匹配有效且高效**：推导了线性对比学习下双层优化的闭式解，无需轨迹存储和长程展开，内存与时间开销极低。
3. **主要性能提升**：在Flickr30K上500对时平均准确率38.4%，比LoRS（31.6%）高6.8个百分点；COCO上500对时19.6% vs 13.5%，提升6.1个百分点。
4. **跨架构泛化能力强**：使用NFNet+BERT蒸馏，在其他架构（NF-ResNet、ViT、DistilBERT）上仍大幅优于基线，而基线方法在架构迁移后甚至低于随机采样。
5. **正则化必要性**：单纯交叉协方差匹配会导致低秩约束不足，加入特征匹配损失（特别是对均值的对齐）可显著改善，且最佳$\lambda$随数据量增加。
6. **视频-文本任务有效**：在WebVid子集上CovMatch同样优于MTT-VL和LoRS，显示通用性。

## 7. 优点
- **理论动机明确**：将双层蒸馏转化为交叉协方差对齐问题，并给出闭式解推导，非启发式。
- **可扩展性极佳**：不需要存储专家轨迹，内存和计算成本与模型大小线性相关，可在单卡A100上完成常见规模的蒸馏。
- **方法简洁优雅**：损失函数仅为Frobenius范数与MMD项，无复杂架构改动。
- **性能领先**：在多个指标和数据集上取得SOTA，且提升幅度显著（6~7%绝对）。
- **跨架构鲁棒**：蒸馏数据可用于不同编码器结构，实用性强。
- **实验全面**：涵盖多数据集、多蒸馏规模、多消融、跨架构、视频扩展，分析深入。

## 8. 不足与局限
1. **假设依赖预训练编码器**：方法假设已有高质量的单模态预训练网络（如ImageNet预训练的NFNet、BERT），未探索从零训练场景。这可能限制了其在完全新领域（如无预训练模型的食品图像）的应用。
2. **线性对比损失的近似性**：推导基于线性对比损失（高温极限近似），与真实InfoNCE存在差距，尽管实验表现良好，但理论近似误差未量化。
3. **合成图像质量**：可视化显示蒸馏后的图像呈现DeepDream风格的高频伪影（图8），可能不利于直观理解。
4. **数据集规模局限**：实验仅限于Flickr30K和COCO（最大123K），未在更大规模（如CC3M/12M）上验证。虽然计算资源允许，但论文未做该实验。
5. **超参数敏感性**：ρ和λ需要根据合成对数量调整，且最佳值变化规律明显（如ρ在少样本时更大），可能需要针对新任务调参。
6. **未与更多蒸馏方法对比**：未与IDC、DATM、R-MTD等更近期单模态蒸馏方法的多模态扩展比较，尽管其已在其他论文中做类似扩展。
7. **鲁棒性验证**：仅报告5次实验的平均与标准差，未讨论更极端的随机种子差异。另外，文本检索指标TR@1较低（Flickr30K 500对仅19.9%），距离真实数据训练（61.6%）仍有很大差距，暗示蒸馏效果仍有限。

（完）
