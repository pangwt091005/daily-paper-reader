---
title: Modeling Caption Diversity in Contrastive Vision-Language Pretraining
title_zh: 对比视觉-语言预训练中的描述多样性建模
authors: "Samuel Lavoie, Polina Kirichenko, Mark Ibrahim, Mido Assran, Andrew Gordon Wilson, Aaron Courville, Nicolas Ballas"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=iaV2fU6Dif"
tags: ["query:nutritionk"]
score: 6.0
evidence: 建模图像描述多样性改进视觉语言预训练
tldr: "CLIP等模型将图像和描述映射为单一向量，限制了多样性表达。Llip通过让图像编码器输出多种视觉特征并依据文本信息混合，来建模同一图像的不同描述方式。实验表明Llip在零样本分类等任务上平均提升2.9%，更丰富的表示有助于食品营养预测等下游任务。"
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 701, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 892, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 811, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 811, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 805, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 864, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 726, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 866, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-iav2fu6dif/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 852, \"height\": 728, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-iav2fu6dif/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1594, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-iav2fu6dif/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1395, \"height\": 532, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-iav2fu6dif/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1596, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-iav2fu6dif/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 916, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-iav2fu6dif/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1075, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-iav2fu6dif/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1043, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-iav2fu6dif/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1078, \"height\": 200, \"label\": \"Table\"}]"
motivation: CLIP模型将图像和描述编码为单一向量，难以表达同一图像的多种描述方式。
method: 提出Llip，视觉编码器输出一组视觉特征，基于文本信息条件混合得到最终表示。
result: "在多项任务上优于CLIP和SigLIP，零样本分类平均提升2.9%。"
conclusion: Llip的多样性建模增强了多模态表示能力，可应用于食品图像营养分析中的细粒度描述。
---

## Abstract
There are a thousand ways to caption an image. Contrastive Language Pretraining (CLIP) on the other hand, works by mapping an image and its caption to a single vector -- limiting how well CLIP-like models can represent the diverse ways to describe an image. In this work, we introduce Llip, Latent Language Image Pretraining, which models the diversity of captions that could match an image. Llip's vision encoder outputs a set of visual features that are mixed into a final representation by conditioning on information derived from the text. We show that Llip outperforms non-contextualized baselines like CLIP and SigLIP on a variety of tasks even with large-scale encoders. Llip improves zero-shot classification by an average of 2.9% zero-shot classification benchmarks with a ViT-G/14 encoder. Specifically, Llip attains a zero-shot top-1 accuracy of 83.5% on ImageNet outperforming a similarly sized CLIP by 1.4%. We also demonstrate improvement on zero-shot retrieval on MS-COCO by 6.0%. We provide a comprehensive analysis of the components introduced by the method and demonstrate that Llip leads to richer visual representations.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：CLIP 等对比视觉-语言预训练模型将图像及其对应描述编码为单一向量，强制图像与文本表示之间的不变性，忽略了同一图像可能对应多种不同描述的多样性（例如“斑马” vs “在卢旺达拍摄”）。这种“一对多”关系被单向量限制，导致表示能力不足。
- **意义**：提出 Llip（Latent Language Image Pretraining），通过显式建模描述多样性，使视觉表示根据文本上下文动态调整，从而获得更丰富的视觉特征，提升零样本分类、检索等下游任务性能。

## 2. 方法论

### 核心思想
- 将图像到文本的映射建模为“一对多”函数：给定一张图像，通过引入从文本中推断的潜在上下文变量，生成不同上下文下的不同视觉表示。

### 关键技术细节
- **视觉编码器**：使用 Vision Transformer (ViT)，在输入序列中额外添加 K 个可学习的 **视觉混合 token**（mixture tokens）。
- **文本编码器**：同 CLIP，输出单一文本特征向量。
- **上下文化**：通过**多头交叉注意力**实现。文本特征作为 Query，视觉混合 token 作为 Key/Value，计算每个头中对应每个混合 token 的权重（softmax 温度参数 τ），加权求和后拼接并投影得到最终上下文视觉表示 \( \hat{z}_{ij} \)。
- **训练目标**：采用 SigLIP 的 sigmoid 对比损失（公式 3），在正负样本对间进行对比学习。由于负样本对中不同图像的 caption 对同一图像是负的，因此可以避免网络仅依赖文本忽略图像的捷径解。
- **推理**：零样本分类时，需将图像与每个类别标签编码，得到上下文视觉表示后计算余弦相似度。

### 公式流程（文字说明）
1. 输入图像 \( x_i \) → 视觉编码器输出 K 个混合 token \( h_i^k \)。
2. 输入文本 \( t_j \) → 文本编码器输出特征 \( g_j \)。
3. 交叉注意力：\( Q = g_j W_Q, K = h_i^k W_K, V = h_i^k W_V \)。
4. 计算加权和 \( z_{ij} \)，归一化后与文本特征 \( \hat{z}'_j \) 计算对比损失。

## 3. 实验设计

- **数据集**：使用 MetaCLIP 数据集（2.5B 图像-文本对，来自 Common Crawl），与 MetaCLIP 相同的过滤策略。
- **Benchmark**：零样本分类（22 个标准基准，包括 ImageNet、CIFAR、Food-101、CUB、SUN397、Cars、Aircraft、Pets、Flowers、MNIST、STL-10、GTSRB、DTD、EuroSAT、RESISC45、PCAM、Country211、KITTI、UCF101、MIT-States 等）；零样本检索（Flickr30k 和 MSCOCO 的 Image→Text 和 Text→Image）。
- **对比方法**：
  - CLIP (Radford et al., 2021)
  - SigLIP (Zhai et al., 2023)
  - MetaCLIP (Xu et al., 2023)
  - OpenCLIP (Cherti et al., 2023)
  - EVA-CLIP (Sun et al., 2023)
  - CLIPA-v2 (Li et al., 2023d)
  - DFN (Fang et al., 2024)
- **骨干网络**：ViT-B/32, ViT-B/16, ViT-L/14, ViT-H/14, ViT-G/14。

## 4. 资源与算力

- **预训练数据**：2.5B 图像-文本对，总样本量 12.8B（12.8 billion pairs seen）。
- **批量大小**：32,768。
- **硬件**：
  - ViT-B 和 ViT-L：128 块 V100 或 A100 GPU。
  - 更大模型（ViT-H/14 和 ViT-G/14）：256 块 A100 80GB GPU。
- **优化**：AdamW（β2=0.95），学习率等超参数同 CLIP/MetaCLIP。使用 PyTorch 编译、混合精度训练、梯度检查点以减少显存。
- **额外计算开销**：推理时 Llip 的计算量随编码器规模增大而接近 CLIP（如图 1b 和 8a）；预训练中主要额外开销来自额外的混合 token 在视觉 Transformer 中的计算（如图 8b），而非交叉注意力本身。

## 5. 实验数量与充分性

- **实验数量**：大量，包括：
  - 与 CLIP/SigLIP 的公平对比（相同数据、相同训练设置）在 5 种骨干上（表 1、表 2）。
  - 与 SOTA 方法的非完全公平对比（表 3、图 4）。
  - 逐步消融实验（从 SigLIP → +Register → +Average → +Learned Average → Llip，图 3）。
  - 超参数分析：混合 token 数 K（1~128）和 softmax 温度 τ（1~10）（图 6）。
  - 表示丰富性分析：奇异值谱（图 5）。
  - 单独场景/视频任务分析（表 7）、地理多样性分析（表 6）、鲁棒性分析（表 5）。
- **充分性与公平性**：
  - 控制变量：所有 Llip 和基线使用同一预训练数据集、相同训练超参（除 Llip 特有参数外），比较 apples-to-apples。
  - 消融实验逐步添加组件，验证每个模块的必要性。
  - 实验覆盖多个任务类型（对象、细粒度、非自然图像、视频、属性识别），结论稳健。
  - 但也承认与 DFN 等方法的比较并非完全公平（DFN 使用更大数据集和更高分辨率）。

## 6. 主要结论与发现

- **零样本分类**：Llip 在所有骨干上一致优于 CLIP 和 SigLIP。以 ViT-G/14 为例，平均提升 2.9%；ImageNet top-1 达 83.5%，超过 MetaCLIP 1.4%。
- **零样本检索**：MSCOCO Image→Text 提升 6.0%（ViT-G/14），Flickr30k 和 MSCOCO 各项指标均提升。
- **表示丰富性**：Llip 的视觉特征奇异值谱衰减更慢，表明学习到的表示具有更大变异性、更丰富。
- **关键组件**：文本条件化的混合权重（而非均匀或固定加权）是性能提升的核心（图 3）。
- **可扩展性**：Llip 随混合 token 数 K 增加和骨干规模增大而性能提升；额外计算开销在大型编码器中相对较小。

## 7. 优点

- **方法简洁有效**：仅添加 K 个可学习 token 和一层交叉注意力，大幅提升性能，不改变编码器主体结构。
- **建模多样性**：直接解决 CLIP 的“单向量”局限，提供更灵活的图像-文本匹配。
- **公平实验**：严格控制数据集、训练设置、骨干规模，与基线进行公平对比。
- **充分消融**：逐步分解各组件贡献，明确验证上下文混合的必要性。
- **全面评估**：覆盖分类、检索、鲁棒性、地理多样性、视频理解等多样任务，且分析表示质量（奇异值谱）。

## 8. 不足与局限

- **实验覆盖的局限**：
  - 未在更大规模数据集（如 DFN 使用的 5B 质量筛选数据）上验证；也未见在更高输入分辨率（如 378）上的实验。
  - 部分任务（如 KITTI、UCF101）上 Llip 提升幅度较小，甚至 MIT-States 上略低于 MetaCLIP（表 1 中 ViT-L/14 的 MIT-States 结果）。
- **推理成本**：零样本分类时需为每个类别对图像进行上下文编码，计算量略高于 CLIP（但随骨干增大而可忽略，如图 8a）。
- **超参数敏感度**：softmax 温度 τ 需要调优（大温度导致性能下降），且未在所有模型上搜索最优 τ（仅对 ViT-B/32 调整）。
- **潜在偏差风险**：训练数据来自 Common Crawl，可能存在地理、文化偏向；虽然分析了地理多样性，但未深入讨论公平性影响。
- **未见探究**：未考虑与字幕生成、多模态对话等任务结合的扩展性，也未探讨在掩码建模等非对比框架下的适用性。

（完）
