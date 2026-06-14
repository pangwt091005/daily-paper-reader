---
title: "CovMatch: Cross-Covariance Guided Multimodal Dataset Distillation with Trainable Text Encoder"
title_zh: CovMatch：基于跨协方差引导的可训练文本编码器多模态数据集蒸馏
authors: "Yongmin Lee, Hye Won Chung"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2dpiR9fqUk"
tags: ["query:nutritionk"]
score: 6.0
evidence: 多模态数据集蒸馏用于视觉语言模型
tldr: 针对多模态数据集蒸馏中冻结文本编码器导致语义对齐受限的问题，本文提出CovMatch框架，通过可训练文本编码器和跨协方差对齐策略，在保持高效训练的同时大幅提升跨模态语义对齐质量。实验表明，该方法在多个下游任务上显著优于现有蒸馏方法，为高效训练大规模视觉语言模型提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 402}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 332}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 527}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 745, \"height\": 352}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1161, \"height\": 351}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 359}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 1198}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2dpir9fquk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 687}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 276}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1318, \"height\": 247}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 588}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 997, \"height\": 421}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1045, \"height\": 345}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1175, \"height\": 301}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1217, \"height\": 261}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1271, \"height\": 223}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1340, \"height\": 261}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 827, \"height\": 182}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 709, \"height\": 134}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1194, \"height\": 225}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 631, \"height\": 141}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1423, \"height\": 821}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1458, \"height\": 849}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2dpir9fquk/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1454, \"height\": 1377}]"
motivation: 现有方法冻结文本编码器导致语义对齐瓶颈，亟需可扩展的蒸馏框架。
method: 提出CovMatch，利用跨协方差匹配真实与合成特征的分布，并联合训练文本编码器。
result: 在多个基准上超越现有蒸馏方法，实现更优的跨模态对齐与模型性能。
conclusion: CovMatch为多模态数据集蒸馏提供了可扩展且语义更强的方案。
---

## Abstract
Multimodal dataset distillation aims to synthesize a small set of image-text pairs that enables efficient training of large-scale vision-language models. While dataset distillation has shown promise in unimodal tasks, extending it to multimodal contrastive learning presents key challenges: learning cross-modal alignment and managing the high computational cost of large encoders. Prior approaches address scalability by freezing the text encoder and update only the image encoder and text projection layer.  However, we find this severely limits semantic alignment and becomes a bottleneck for performance scaling.
We propose CovMatch, a scalable dataset distillation framework that aligns the cross-covariance of real and synthetic features while regularizing feature distributions within each modality. Unlike prior approaches, CovMatch enables joint optimization of both encoders, leading to stronger cross-modal alignment and improved performance. Evaluated on Flickr30K and COCO, CovMatch outperforms state-of-the-art multimodal distillation methods and achieves up to 6.8\% absolute gains in retrieval accuracy using only 500 synthetic pairs.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

多模态数据集蒸馏旨在从大规模图像-文本数据中合成一个小型但具有代表性的样本集，从而高效训练视觉-语言模型（如CLIP）。现有方法（如MTT-VL、LoRS）通常冻结文本编码器（如BERT），仅更新图像编码器和投影层，以缓解双向优化带来的高计算和存储开销。然而，作者发现冻结文本编码器严重限制了跨模态语义对齐能力，导致检索性能随着合成数据规模增加而饱和甚至下降。因此，迫切需要一种能够联合优化双编码器、同时保持可扩展性的蒸馏框架。

## 2. 方法论：核心思想、关键技术细节、算法流程

**核心思想**：将多模态对比学习中的内层优化（仅优化线性投影层）近似为闭式解，将双层蒸馏目标转化为真实数据与合成数据跨协方差矩阵的对齐问题，从而避免昂贵的轨迹展开或存储专家轨迹。

**关键技术细节**：
- **线性对比损失近似**：采用高温近似将InfoNCE损失简化为线性形式，该线性损失等价于迹形式的交叉协方差项加正则项。
- **闭式解推导**：固定双编码器，仅优化投影层时，内层优化有闭式解：最优投影乘积 \( \hat{G}_v^\top \hat{G}_l = \frac{1}{\rho} C_S \)。代入外层损失后，目标简化为最大化 \( \text{Tr}(C_T^\top C_S) \)。
- **交叉协方差匹配损失**：为避免迹目标不稳定，改用Frobenius范数：\( L_{\text{cov}} = \|\rho C_T - C_S\|_F^2 \)。
- **特征匹配正则项**：为防止低秩协方差矩阵导致欠约束，额外添加各模态投影后特征的均值差异（最大均值差异）损失：\( L_{\text{feat}}^m = \| \frac{1}{|T|}\sum G_m f_m(\cdot) - \frac{1}{|S|}\sum G_m f_m(\hat{\cdot}) \|^2 \)。
- **联合损失**：\( L_{\text{CovMatch}} = L_{\text{cov}} + \lambda (L_{\text{feat}}^v + L_{\text{feat}}^l) \)。
- **在线模型更新**：每次蒸馏步骤前，用真实数据的一个批次对双编码器和投影层进行一次梯度更新，防止过拟合到固定模型状态；并每T步重置模型到预训练权重和随机投影。

**算法流程**（Algorithm 1）：
1. 初始化合成数据集S（随机选取真实对），加载预训练图像和文本编码器，随机初始化投影层。
2. 重复直到收敛：
   - 采样真实小批次 \( B_T \sim T \) 和合成批次 \( B_S \sim S \)。
   - 计算匹配损失 \( L_{\text{CovMatch}} \)。
   - 更新S：\( S \leftarrow S - \alpha \nabla_S L_{\text{CovMatch}} \)。
   - 用真实数据T训练模型（编码器和投影层）一步。
3. 输出合成数据集S。

## 3. 实验设计

**数据集与基准**：
- **图像-文本检索**：Flickr30K（~31K图像，5 caption/图像，Karpathy splits）和COCO（123K图像，5 caption/图像）。
- **评估指标**：Recall@K（K=1,5,10）对图像→文本（TR@K）和文本→图像（IR@K），报告平均值。
- **网络架构**：默认图像编码器为NFNet-L0，文本编码器为BERT-base。跨架构实验额外使用NF-ResNet50、NF-RegNet、ViT-B/16以及DistilBERT。

**对比方法**：
- **核心集选择**：Random、Herding、K-Center。
- **数据集蒸馏**：MTT-VL（双轨迹匹配，冻结文本编码器）、LoRS（低秩相似度挖掘，冻结文本编码器）。
- 所有基线在评估时均使用完整网络训练（除MTT-VL/LoRS因冻结文本编码器只能更新投影层）。

**实验设置**：
- 合成数据规模：100/200/500对（分别占Flickr30K的0.3%/0.7%/1.7%，COCO的0.1%/0.2%/0.4%）。
- 蒸馏超参数：学习率1.0，动量0.5，ρ=2（100对）或1（200+/500+），λ=0.1（100/200对）或0.6/0.5（500对），迭代10,000-20,000次，在线模型每50步重置。
- 评估训练：SGD，动量0.9，权重衰减5e-4，batch size 128，学习率0.01（编码器）和0.1（投影层），100 epochs，50 epoch衰减。

**补充实验**：视频-文本检索（WebVid子集，VideoResNet+BERT）、不同架构蒸馏、消融实验（缩放因子ρ、特征匹配权重λ、在线更新策略、batch size、投影维度、投影深度、单模态蒸馏、冻结文本编码器对比）。

## 4. 资源与算力

论文中明确给出了资源对比（Table 1）：
- **MTT多模态**：专家轨迹存储 >120GB，蒸馏耗时132h，内存71GB，每迭代16.9秒（A100 80GB）。
- **Tesla多模态**：存储 >120GB，耗时132h，内存22GB，每迭代19.2秒。
- **CovMatch**：无需专家轨迹，存储0GB，内存15GB，每迭代1.2秒。蒸馏时间未明确总时长，但10,000迭代约需3.3小时（单卡A100 80GB）。实验均在单个A100 80GB GPU上完成，未提及使用多卡。

## 5. 实验数量与充分性

论文进行了大量实验以确保结论的可靠性：
- **主实验结果**（Table 2）：Flickr30K和COCO上3种合成规模（100/200/500），每种重复5次报告均值和标准差。
- **跨架构泛化**（Table 3）：4种图像编码器+2种文本编码器组合，共8种架构，合成规模100。
- **视频-文本检索**（Appendix D）：1种合成规模（500），对比3个基线。
- **消融实验**（Section 4.3, Appendix E）：
  - 缩放因子ρ（ρ=1,2,3,4）
  - 特征匹配权重λ（0,0.1,0.25,0.5,0.75,1.0）
  - 在线更新策略（固定、用S更新、用T更新）
  - batch size（64,128,256,512,1024）
  - 投影维度（256,768,2304,4096）
  - 投影深度（1,2,3）
  - 单模态冻结（仅图像/仅文本）
  - 文本编码器冻结策略对比（蒸馏/评估阶段冻结/解冻）
- **定性分析**：t-SNE可视化、检索示例（Figure 2,6,7）。

实验设计全面，覆盖了主要超参数、架构变体、模态冻结策略，且重复多次报告误差，结果客观充分。

## 6. 主要结论与发现

- **核心发现**：冻结文本编码器是限制多模态数据集蒸馏性能缩放的关键瓶颈。CovMatch通过联合优化双编码器，显著提升了语义对齐效果（类内/类间相似度差距增大）。
- **性能提升**：在Flickr30K（500对）上平均检索精度达到38.4%，比最优基线LoRS（31.6%）提升6.8%绝对值；COCO上达到19.6% vs 13.5%，提升6.1%。
- **跨架构泛化**：CovMatch蒸馏的数据集在多种未见架构上均优于或接近随机选择，而基线方法在替换架构后性能退化严重（甚至不如随机）。
- **视频-文本扩展**：CovMatch在视频-文本检索上也取得最佳结果（Average 11.0% vs LoRS 8.3%）。
- **消融结论**：
  - 缩放因子ρ在样本少时更重要（需强正则化）。
  - 特征匹配损失λ随合成样本数增加而增大（防止仅对齐二阶统计量导致分布偏移）。
  - 用真实数据更新在线模型优于用合成数据更新或固定模型。
- **效率优势**：CovMatch无需专家轨迹，内存需求仅15GB，每迭代1.2秒，远低于MTV-VL/Tesla的71GB/22GB和16.9/19.2秒。

## 7. 优点

1. **高效可扩展**：闭式解推导避免了轨迹展开和存储，大幅降低计算和内存成本，使得在消费级GPU（A100 80GB）上即可完成蒸馏。
2. **联合优化编码器**：首次在多模态蒸馏中支持可训练文本编码器，突破语义对齐瓶颈，性能随合成数据规模持续增长。
3. **理论指导**：从线性对比损失出发，推导出交叉协方差对齐的简洁形式，为方法提供理论依据。
4. **跨架构泛化强**：蒸馏数据集对不同网络结构（包括ViT、DistilBERT）泛化良好，说明方法学习到的是更通用的表示而非过拟合特定架构。
5. **消融全面**：对每个关键组件（缩放因子、特征匹配、在线更新、batch size、投影设计等）均进行了细致分析，验证了设计的必要性。
6. **可迁移性**：除图像-文本外，在视频-文本任务上也有出色表现，表明框架可推广到其他模态组合。

## 8. 不足与局限

1. **假设预训练编码器可用**：方法依赖预训练好的单模态编码器（如ImageNet预训练NFNet、BERT），未探索从零开始训练的情况。文中明确列为未来工作。
2. **合成图像质量并非关注点**：可视化显示蒸馏后的图像具有高频“DeepDream”风格，可能缺乏自然语义，但论文的优化目标仅为匹配交叉协方差，不保证图像可解释性。
3. **实验数据集规模有限**：主实验仅使用Flickr30K（31K）和COCO（123K），未在更大规模（如CC12M、LAION-400M）上验证可扩展性。
4. **蒸馏时间未与精度权衡充分量化**：虽给出每迭代时间，但未比较达到同等性能所需的总时间与基线方法的差异（例如，CovMatch迭代10K次，而MTT-VL需要132h训练专家轨迹+蒸馏）。
5. **超参数敏感**：缩放因子ρ和特征匹配权重λ需根据合成数据规模调整（如100对时ρ=2，500对时λ=0.6），可能阻碍在更复杂场景下的自动调参。
6. **线性损失近似限制**：高温近似在高相似度时可能失效，论文仅在附录C中提供推导，未讨论温度选择或偏离线性假设时的鲁棒性。
7. **仅评估检索任务**：未验证生成、分类等其他多模态下游任务上的蒸馏效果。

（完）
