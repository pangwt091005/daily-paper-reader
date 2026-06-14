---
title: Vision-Language Models are Strong Noisy Label Detectors
title_zh: 视觉语言模型是强大的噪声标签检测器
authors: "Tong Wei, Hao-Tian Li, Chun-Shu Li, Jiang-Xin Shi, Yu-Feng Li, Min-Ling Zhang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=haUnEiXgQ7"
tags: ["query:nutritionk"]
score: 5.0
evidence: 视觉语言模型用于噪声标签检测
tldr: 该论文针对视觉语言模型微调时标签噪声问题，提出去噪微调框架DeFT，通过为正负类别学习特征提示，利用预训练的图文对齐能力筛选出噪声标签。实验表明DeFT在多个基准上有效提升了噪声环境下的微调性能，为食品营养预测中标注不准确的数据集提供了清洗与稳健训练方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 723, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1362, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-hauneixgq7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1420, \"height\": 327, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 1090, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1044, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 721, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1460, \"height\": 1218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1368, \"height\": 684, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-hauneixgq7/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1020, \"height\": 210, \"label\": \"Table\"}]"
motivation: 真实应用中标签噪声阻碍视觉语言模型微调，需自动检测噪声。
method: 利用预训练图文对齐，为每个类别学习正负提示以识别噪声样本。
result: 在多种噪声率下，DeFT显著提升了微调模型的精度。
conclusion: 视觉语言模型可有效作为噪声标签检测器，降低标注成本。
---

## Abstract
Recent research on fine-tuning vision-language models has demonstrated impressive performance in various downstream tasks. However, the challenge of obtaining accurately labeled data in real-world applications poses a significant obstacle during the fine-tuning process. To address this challenge, this paper presents a Denoising Fine-Tuning framework, called DeFT, for adapting vision-language models. DeFT utilizes the robust alignment of textual and visual features pre-trained on millions of auxiliary image-text pairs to sieve out noisy labels. The proposed framework establishes a noisy label detector by learning positive and negative textual prompts for each class. The positive prompt seeks to reveal distinctive features of the class, while the negative prompt serves as a learnable threshold for separating clean and noisy samples. We employ parameter-efficient fine-tuning for the adaptation of a pre-trained visual encoder to promote its alignment with the learned textual prompts. As a general framework, DeFT can seamlessly fine-tune many pre-trained models to downstream tasks by utilizing carefully selected clean samples. Experimental results on seven synthetic and real-world noisy datasets validate the effectiveness of DeFT in both noisy label detection and image classification. Our source code can be found in the supplementary material.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究问题**：视觉语言模型（如CLIP）在微调至下游任务时，面临真实世界数据集常包含大量噪声标签（错误标注）的问题，导致模型性能显著下降。
- **背景**：现有的噪声标签学习方法大多针对单模态模型从零训练，未充分利用多模态预训练模型的强大图文对齐能力。同时，全微调（FFT）在噪声数据下易导致特征扭曲，而参数高效微调（PEFT）和文本提示调优对噪声更鲁棒，但尚未被系统用于噪声检测。
- **核心动机**：利用CLIP等预训练视觉语言模型固有的图文特征对齐能力，构建一个无需先验噪声率的、通用的噪声标签检测器，从而在噪声数据下实现鲁棒的微调。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：为每个类别学习一对正、负文本提示（positive/negative prompts），将噪声检测转化为二分类任务：若样本与正提示的相似度高于与负提示的相似度，则视为干净样本。
- **关键技术细节**：
  - **Dual Prompt设计**：正提示 `prompt_k^+` 旨在捕捉该类别的判别性特征；负提示 `prompt_k^-` 作为一个可学习的、样本依赖的阈值。
  - **噪声检测标准**：对于标签为k的样本xi，计算其视觉特征与正/负文本特征的余弦相似度。若 `sim(I_i, T_k^+) > sim(I_i, T_k^-)`，则视为干净样本 `D_clean`。
  - **优化目标**：
    - 二元分类损失 `L_dp`：利用伪标签（由零样本CLIP预测）作为正样本，随机互补标签（negative learning）作为负样本，训练双提示。
    - 对比对齐损失 `L_sim`：在干净子集上最大化图像与正文本特征的匹配，同时用PEFT（如VPT）微调视觉编码器以增强图文对齐。
  - **两阶段框架**：
    - **第一阶段**：学习噪声标签检测器（优化双提示和PEFT模块）。
    - **第二阶段**：利用第一阶段选出的干净样本，移除PEFT模块，改用全微调（FFT）训练线性分类器，进一步提升任务精度。
- **算法流程**（文字说明）：
  1. 使用原始噪声数据对模型进行1个epoch的预热。
  2. 计算每个样本的净概率 `p_clean`，按式(5)筛选干净子集。
  3. 联合优化 `L_dp + L_sim` 更新双提示和视觉PEFT参数。
  4. 固定第一阶段选择的干净子集，移除PEFT，全微调视觉编码器和随机初始化的线性分类器（交叉熵损失），训练10个epoch。

## 3. 实验设计：数据集、基准与对比方法

- **数据集**：
  - **合成噪声数据集**：CIFAR-100、Tiny-ImageNet、Stanford-Cars、CUB-200-2011。噪声类型包括对称噪声（r=0.2/0.4/0.6）和实例依赖噪声（r=0.2/0.3/0.4）。
  - **真实噪声数据集**：CIFAR-100N（≈40%噪声）、Clothing1M（≈40%噪声）、WebVision（≈20%噪声）。
- **基准方法**：
  - 噪声检测对比：Label-match（零样本预测一致）、Small-loss（基于损失选择）。
  - 分类任务对比：Cross-Entropy (CE)、Symmetric CE (SCE)、Early-Learning Regularization (ELR)、DivideMix (GMM) 以及近年SOTA：RoLT、UNICON、LongReMix、ProMix。
- **评价指标**：噪声检测用精确率（Precision）、召回率（Recall）；分类用最佳测试精度（Best）和最后测试精度（Last）。

## 4. 资源与算力

- 论文明确说明：所有实验在一张 **NVIDIA GeForce RTX 3090 GPU** 上完成。
- 未提及具体训练时长（但注明两个阶段各训练10个epoch，总epoch数20，计算开销很小）。

## 5. 实验数量与充分性

- **实验数量**：
  - 噪声检测实验：在4个合成数据集×6种噪声设置（共24组），加上CIFAR-100N真实噪声检测，以及高噪声（80%对称、50%实例依赖）的额外实验。
  - 分类实验：4个合成数据集×6种噪声设置（24组），3个真实数据集，以及不同PEFT技术对比、不同视觉架构（ViT-B/16、ResNet-50、ConvNeXt-T、MAE-ViT-B）的泛化性实验。
  - 消融实验：模型适应阶段必要性（w/o adap、PEFT、FFT）、文本提示长度/视觉提示长度/训练epoch的敏感性分析。
- **充分性与客观性**：
  - 覆盖多种噪声类型（对称、实例依赖、真实噪声）和多种噪声率（20%~80%），且与多种基线方法公平比较（使用相同预训练CLIP模型，微调阶段统一用FFT）。
  - 在真实噪声数据集上额外对比了近年SOTA（RoLT等），并采用两阶段评估确保公平。
  - 提供了不同视觉架构的实验，验证了框架通用性。
  - 总体实验设计较为充分、客观。

## 6. 论文的主要结论与发现

- 视觉语言模型（CLIP）可以作为一种强大的噪声标签检测器，通过双提示学习实现无需先验噪声率的高精度样本筛选。
- 参数高效微调（PEFT）相比全微调（FFT）在噪声数据下更鲁棒，能够更好保持预训练特征；而FFT在干净数据上表现更优，因此第二阶段使用FFT可进一步提升性能。
- 提出的DeFT框架在合成和真实噪声数据集上的噪声检测和分类任务均显著优于现有方法，尤其是在细粒度数据集和高噪声场景下提升明显。
- 双提示方法能够自动确定阈值，避免了对噪声率的依赖，且与多种预训练模型兼容。

## 7. 优点

- **方法创新**：首次将视觉语言模型的图文对齐能力用于噪声标签检测，提出正负双提示的可学习阈值方案，摆脱了对噪声率的先验需求。
- **简洁高效**：两阶段框架简单，仅需20个epoch训练，计算开销小；且无需依赖训练样本的动态信息（如损失分布），适用于在线或批次处理。
- **鲁棒性与通用性**：在对称噪声、实例依赖噪声、真实噪声下均表现优异；可无缝适配不同视觉架构（ResNet、ViT、ConvNeXt、MAE）。
- **深入分析**：提供了大量消融和敏感性实验，验证了每一设计选择（如PEFT vs FFT、双提示的阈值作用）的有效性。

## 8. 不足与局限

- **应用限制**：
  - 当前仅处理单标签多类分类任务中的图像-标签噪声，未扩展至多标签分类或图像-文本对噪声。
  - 方法依赖预训练的视觉语言模型（如CLIP），若缺乏此类模型或任务领域与预训练数据差异极大，可能效果受限。
- **实验覆盖**：
  - 未在更大规模噪声数据集（如Red Mini-ImageNet、真实噪声的WebVision全量）上验证。
  - 未与基于噪声转移矩阵估计的方法（如CausalNL）对比。
- **偏差风险**：第一阶段依赖零样本CLIP生成伪标签，若CLIP对某些类别本身预测偏差较大，可能引入检测偏差。
- **局限性说明**：论文自身在附录A.4中明确指出了当前算法仅处理单标签多类分类的局限，并建议未来推广至多标签或图文对噪声场景。

（完）
