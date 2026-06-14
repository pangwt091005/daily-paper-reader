---
title: Kernel-based Unsupervised Embedding Alignment for Enhanced Visual Representation in Vision-language Models
title_zh: 基于核的无监督嵌入对齐以增强视觉语言模型中的视觉表示
authors: "Shizhan Gong, Yankai Jiang, Qi Dou, Farzan Farnia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0fLoGPTLo1"
tags: ["query:nutritionk"]
score: 6.0
evidence: 增强视觉语言模型的细粒度视觉表示，有利于食品识别与营养分析
tldr: 现有视觉语言模型（如CLIP）在细粒度感知上存在局限，影响下游多模态理解任务。本工作提出一种基于核的无监督嵌入对齐方法，将CLIP的视觉表示与DINOv2的细粒度特征对齐，同时保持与文本嵌入的兼容性。实验验证对齐后的表示在多种视觉任务上性能提升。该工作为食品图像营养成分预测等需要精细视觉理解的场景提供了更好的视觉特征基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1737, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 807, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1736, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1736, \"height\": 350, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1776, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 885, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 627, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1562, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 926, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1773, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1616, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 844, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1773, \"height\": 420, \"label\": \"Table\"}]"
motivation: 针对CLIP模型细粒度感知能力不足的问题，提出核方法对齐CLIP与DINOv2表示。
method: 通过核方法无监督对齐CLIP视觉嵌入与DINOv2嵌入，保持文本兼容性。
result: 对齐后的视觉表示在多种任务上性能提升，细粒度感知能力增强。
conclusion: 该工作为视觉语言模型提供更优的视觉特征，可迁移至食品营养预测等下游任务。
---

## Abstract
Vision-language models, such as CLIP, have achieved significant success in aligning visual and textual representations, becoming essential components of many multi-modal large language models (MLLMs) like LLaVA and OpenFlamingo. However, numerous studies have identified CLIP's limited fine-grained perception as a critical drawback, leading to substantial failures in downstream MLLMs. In contrast, vision-centric foundation models like DINOv2 demonstrate remarkable capabilities in capturing fine details from images. In this work, we propose a novel kernel-based method to align CLIP's visual representation with that of DINOv2, ensuring that the resulting embeddings maintain compatibility with text embeddings while enhancing perceptual capabilities. Our alignment objective is designed for efficient stochastic optimization. Following this image-only alignment fine-tuning, the visual encoder retains compatibility with the frozen text encoder and exhibits significant improvements in zero-shot object recognition, fine-grained spatial reasoning, and localization. By integrating the aligned visual encoder, downstream MLLMs also demonstrate enhanced performance. The code and models are available at https://github.com/peterant330/KUEA.

---

## 论文详细总结（自动生成）

# 论文《Kernel-based Unsupervised Embedding Alignment for Enhanced Visual Representation in Vision-language Models》中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：Vision-Language Models（如CLIP）在视觉与文本对齐上表现出色，被广泛用于多模态大语言模型（MLLMs，如LLaVA、OpenFlamingo）的视觉特征提取。然而，CLIP因训练时依赖全局图像-文本对，其视觉编码器在**细粒度感知**（如颜色、空间关系、计数、定位）上存在显著缺陷，导致下游MLLMs在这些任务上失败。
- **问题**：现有增强CLIP视觉能力的方法（如多编码器集成、掩码微调、区域级训练）或引入巨大计算开销，或破坏视觉-文本对齐（需重新训练下游模型），实用性低。
- **动机**：DINOv2等视觉自监督模型在捕获图像细节上优于CLIP。提出一种**轻量级、无监督的嵌入对齐方法**，在不重新训练文本编码器或下游LLM的前提下，将CLIP视觉表示与DINOv2对齐，提升其细粒度感知能力，同时保持零样本泛化与文本兼容性。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：通过核函数（Kernel Function）对齐CLIP与DINOv2的**样本间相似性关系**（而非直接对齐特征空间），并加入正则化项约束CLIP特征不偏离原始方向，从而保持文本对齐。
- **关键技术细节**：
  - **核函数**：使用归一化的多项式核（degree=3），公式：  
    \( k_{polynomial}(x, y) = (\gamma x^\top y + c)^d \)，并归一化使 \( k(x, x)=1 \)。
  - **优化目标**（公式6）：
    \[
    \min_\theta\; w \cdot \mathbb{E}_{I_i,I_j} \big[ (k_1(f_\theta(I_i), f_\theta(I_j)) - k_2(g(I_i), g(I_j)))^2 \big] + \mathbb{E}_{I_i} \big[ \|f_\theta(I_i) - f_{\theta_0}(I_i)\|_2^2 \big]
    \]
    - 第一项：对齐CLIP（k₁）与DINOv2（k₂）的核矩阵。
    - 第二项：L2正则化，防止CLIP特征偏离原始预训练方向（从而保持文本对齐）。
    - w为平衡系数。
  - **计算可行性**：利用Hoeffding不等式证明可使用随机小批量梯度下降高效优化（Proposition 3.1）。每次采样图像对计算核差异。
  - **训练细节**：仅使用图像数据（ImageNet-1K训练集，128万张），不依赖任何文本或标注。CLIP的文本编码器完全冻结。
- **算法流程**（文字说明）：
  1. 输入批量图像，分别通过CLIP视觉编码器（当前参数θ）和DINOv2编码器（固定）提取特征。
  2. 计算所有图像对之间的归一化多项式核值。
  3. 计算两个核矩阵之间 MSE 作为对齐损失。
  4. 计算 CLIP 当前特征与原始预训练特征间的 L2 距离作为正则化损失。
  5. 总损失 = w × 对齐损失 + 正则化损失，反向传播更新 CLIP 视觉编码器参数。

## 3. 实验设计：数据集、Benchmark、对比方法
- **零样本图像分类**（12个数据集）：ImageNet, CIFAR-10/100, CalTech101, FER2013, OxfordPets, DTD, RESISC45, EuroSAT, PCAM, ImageNet-Sketch, ImageNet-O。采用 CLIP-Benchmark 评估。
- **图像-文本检索**：Flickr30K, MSCOCO（R@1/5/10）。
- **计数/空间推理**：SVHN（数字识别）、GTSRB（交通标志）、CLEVR Distance/Counts。评估方式包括零样本与线性探测。
- **定位能力**：MSCOCO上局部/全局探测（预测每个patch或整图的标签），使用macro-recall。
- **下游MLLM评估**：
  - LLaVA-1.5-7B：VQAv2, TextVQA, RefCOCO系列, VSR, TallyQA, POPE, AI2D, LLaVA-bench等。
  - OpenFlamingo-3B：7个VQA数据集（COCO, Flickr30K, VQAv2, OK-VQA, TextVQA, VizWiz, HatefulMemes），评估0/4/16-shot。
- **对比方法**：
  - 投影法（线性映射DINOv2到CLIP空间），特征对齐（线性变换+ L2损失），DIVA（扩散反馈微调）。
  - AM-RADIO（教师蒸馏），Additive-MoF（特征拼接）。
  - 对多种VLM变体（SigLIP, DFN, MetaCLIP）和不同目标模型（MLCD）也进行了测试。

## 4. 资源与算力
- 文中明确提及：
  - 使用 **2块 NVIDIA RTX 4090 GPU** 完成 ViT-B-16 和 ViT-L-14 的对齐微调。
  - ViT-L-14-336 使用 **4块** 4090 GPU。
  - 对 ViT-L-14，对齐微调耗时约 **30小时**。
- 训练数据：ImageNet-1K（128万张图像），仅需2~4个epoch，算力需求远小于原CLIP预训练。

## 5. 实验数量与充分性
- **实验数量**（共约数十组结果）：
  - 零样本分类（3种CLIP backbone × 12数据集 + 其他VLM对比）。
  - 检索（2数据集 × 3 backbone）。
  - 计数/空间推理（4任务 × 3 backbone，含零样本与线性探测）。
  - 定位探测（3 backbone × 局部/全局）。
  - MLLM：LLaVA（12个benchmark × 多种设置），OpenFlamingo（7数据集 × 3 shots）。
  - 消融实验：训练轮数、正则化项、系数w、核函数选择、数据集大小、不同目标模型等（Fig.3, Table 14等）。
- **充分性与公平性**：
  - 实验覆盖零样本、线性探测、微调、多模态QA等多种场景，且均在标准benchmark上比较。
  - 对比方法（投影、特征对齐、DIVA）合理；控制变量（如单独LLM微调）。
  - 消融实验系统探讨各组件贡献，结论可靠。
- **客观性**：报告了不同backbone和模型尺寸下的收益，无明显选择偏差。

## 6. 主要结论与发现
- 提出的核对齐方法显著提升CLIP视觉表示的细粒度感知能力（零样本分类平均提升0.8%~1.3%），尤其在低分辨率、小物体、计数/空间任务上增益更明显（线性探测最高提升5.5%）。
- 文本对齐和检索性能几乎无损（甚至略有提升），证明了正则化项的有效性。
- 对齐后的视觉编码器可直接替换下游MLLM（LLaVA, OpenFlamingo）的视觉部分，无需额外对齐训练，性能全面提升（LLaVA平均提升1.7%，OpenFlamingo 0.7%~1.7%）。
- 方法具有通用性：可适用于SigLIP、DFN等不同VLM，也可用MLCD等不同目标模型。
- 轻量级：仅需ImageNet-1K微调2~4 epoch，即可取得显著改进。

## 7. 优点
- **方法创新**：首次将核方法用于CLIP与视觉模型的嵌入对齐，通过调整样本间相似性而非直接特征距离，更灵活地保持原有特征空间结构。
- **高效实用**：仅需图像数据，无需文本或标注；微调成本低（30小时/2-4 GPU），且不破坏下游模型兼容性，无需重训LLM。
- **实验充分**：从零样本分类、检索、细粒度任务、定位到下游MLLM全面评估，消融实验覆盖主要设计选择。
- **开源贡献**：代码和模型公开，促进可复现性。

## 8. 不足与局限
- **数据规模有限**：仅使用ImageNet-1K进行微调，未在大规模数据集（如DataComp-1B）上验证；作者也坦承此局限，认为更大数据或能带来更多提升。
- **模型size限制**：仅测试了小规模MLLM（LLaVA-7B, OpenFlamingo-3B），未在更大模型（如70B）上验证效果。
- **目标模型单一**：主要对齐DINOv2，虽扩展了MLCD等，但未全面探索其他视觉中心模型（如MAE、BEiT）。
- **未评估公平性或偏差**：文末提及对远程感知和医疗诊断有潜在影响，但未讨论视觉对齐是否引入或加剧偏差（如种族、性别等）。
- **理论保证有限**：Proposition 3.1仅给出随机梯度估计的收敛概率界，未证明优化目标本身的最优性；正则化对文本对齐的保护是基于L2约束，实际中可能并非最优方式。
- **与最新方法的对比不足**：如AM-RADIO仅在有限数据设置下对比，未在完整预训练规模下公平比较。

（完）
