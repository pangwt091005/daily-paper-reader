---
title: Efficient Multimodal Dataset Distillation via Generative Models
title_zh: 基于生成模型的高效多模态数据集蒸馏
authors: "Zhenghao Zhao, Haoxuan Wang, Junyi Wu, Yuzhang Shang, Gaowen Liu, Yan Yan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Eu2Tqcvxih"
tags: ["query:nutritionk"]
score: 5.0
evidence: 基于生成模型的多模态数据集蒸馏
tldr: 该论文针对现有多模态数据集蒸馏方法计算资源消耗大的问题，提出生成式蒸馏方法EDGE，利用生成模型合成小型但有效的图像-文本数据集。相较于传统轨迹匹配方法，EDGE将蒸馏时间从数天缩短至数小时，同时保持下游性能。在食品营养预测场景中，可用该方法压缩大规模食品图像-营养数据集，提升训练效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-eu2tqcvxih/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 725, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eu2tqcvxih/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eu2tqcvxih/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 731, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eu2tqcvxih/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eu2tqcvxih/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 726, \"height\": 1307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eu2tqcvxih/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 726, \"height\": 1307, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 698, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 701, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 713, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 710, \"height\": 125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 708, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eu2tqcvxih/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 708, \"height\": 147, \"label\": \"Table\"}]"
motivation: 现有数据集蒸馏方法计算代价高，不适合大规模多模态数据。
method: 提出EDGE，利用生成模型直接合成代表性样本，替代轨迹匹配。
result: 在多个多模态数据集上，EDGE以更低成本取得了可比或更优的蒸馏效果。
conclusion: 生成式蒸馏为多模态数据集压缩提供了高效方案。
---

## Abstract
Dataset distillation aims to synthesize a small dataset from a large dataset, enabling the model trained on it to perform well on the original dataset. With the blooming of large language models and multimodal large language models, the importance of multimodal datasets, particularly image-text datasets, has grown significantly. However, existing multimodal dataset distillation methods are constrained by the Matching Training Trajectories algorithm, which significantly increases the computing resource requirement, and takes days to process the distillation. In this work, we introduce EDGE, a generative distillation method for efficient multimodal dataset distillation. Specifically, we identify two key challenges of distilling multimodal datasets with generative models: 1) The lack of correlation between generated images and captions. 2) The lack of diversity among generated samples.
To address the aforementioned issues, we propose a novel generative model training workflow with a bi-directional contrastive loss and a diversity loss. Furthermore, we propose a caption synthesis strategy to further improve text-to-image retrieval performance by introducing more text information.  Our method is evaluated on Flickr30K, COCO, and CC3M datasets, demonstrating superior performance and efficiency compared to existing approaches. Notably, our method achieves results 18$\times$ faster than the state-of-the-art method. Our code will be made public at https://github.com/ichbill/EDGE.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

论文聚焦于**多模态数据集蒸馏**的效率问题。现有方法（如基于匹配训练轨迹的MTT-VL和LoRS）虽然能压缩图像-文本数据集，但计算资源消耗极大：蒸馏500对样本需要4天，峰值内存高达200GB；LoRS蒸馏仅500对样本需约150小时。这严重限制了多模态数据集蒸馏在大型数据集（如CC3M，约300万对）上的实际应用。论文旨在通过生成模型实现高效蒸馏，将时间从数天缩短至数小时，同时保持下游性能。

### 2. 论文提出的方法论

- **核心思想**：利用预训练的扩散模型（Stable Diffusion v1.5）作为生成器，通过微调使其生成的图像-文本对既具备高度相关性，又具备多样性，从而替代传统的MTT优化过程。
- **关键技术细节**：
  - **EDGE扩散微调流程**：对输入图像编码得到潜在表示\(z_0\)，添加噪声得到\(z_t\)，用文本嵌入\(y\)作为条件预测噪声\(\hat{\epsilon}\)，然后通过公式\(z = (z_t - \sqrt{\beta_t} \cdot \hat{\epsilon}) / \sqrt{\alpha_t}\)得到去噪后的图像潜在表示\(z\)。
  - **双向对比损失\(L_C\)**：借鉴InfoNCE，在图像潜在表示\(z_i\)和文本嵌入\(y_i\)之间计算相似度矩阵，分别计算图像到文本和文本到图像的交叉熵损失，促使生成图像与给定文本高度对齐。
  - **多样性损失\(L_D\)**：对每对[\(z_i; y_i\)]的归一化拼接向量计算成对余弦相似度，并最小化这些相似度（即最大化距离），以增加合成样本间的差异。
  - **整体损失**：\(L_{EDGE} = L_C + \lambda L_D\)（实验设\(\lambda=1\)）。
- **文本合成策略**：使用MLLM（如LLaVA）为生成的每张图像生成额外标题，以增加文本信息量，进而提升文本到图像检索性能。

### 3. 实验设计

- **数据集**：Flickr30K（31K图像，每图5标题）、COCO（123K图像，每图5标题）、CC3M（约330万图像-文本对，实际采集到230万对）。
- **基准任务**：图像-文本对比学习（ITC），评价指标为Top-K检索（IR@K表示文本到图像，TR@K表示图像到文本）。
- **对比方法**：随机选择、核心集选择（HERD, K-Center, Forget）、现有VLDD方法（MTT-VL, LoRS）、预训练Stable Diffusion v1.5。消融实验中还对比了不同扩散模型（SD v1.5 vs SD3）、不同MLLM（LLaVA, GPT-4o-mini, Llama）、不同标题数(CPI=1,2,5)等。
- **评估模型**：NFNet（图像编码器）+ BERT-base（文本编码器）；跨架构实验中使用ResNet、RegNet等不同图像编码器。

### 4. 资源与算力

- 所有蒸馏实验在**单张NVIDIA RTX A5000 GPU**上完成。
- 蒸馏时间对比：
  - Flickr30K（500对）：MTT-VL需77.8 GPU时，LoRS需54.2 GPU时，EDGE仅需13.6 GPU时。
  - COCO（500对）：MTT-VL需162.3 GPU时，LoRS需151.6 GPU时，EDGE仅需7.7 GPU时。
  - CC3M（500对）：仅EDGE可行，需31.7 GPU时。
- 峰值内存：MTT-VL蒸馏500对样本需200GB，LoRS约320GB，EDGE仅约20GB（图1示意）。
- 论文未说明训练时的batch大小等具体超参数及总计算量，但附录A给出了学习率、epoch等细节。

### 5. 实验数量与充分性

- **实验组数**：主实验包括3个数据集×2种规模（500/1000对），加上CC3M的少量对比；消融实验涵盖5个方面（组件、扩散模型、CPI、MLLM、跨架构）；另提供了CLIP分数、FID分数、计算效率表等。
- **充分性与公平性**：
  - 与SOTA方法对比时，使用了相同的数据集和评估协议。
  - 跨架构实验表明EDGE方法对架构不敏感，而LoRS在换用不同图像编码器时性能骤降，说明公平对比中EDGE具有更好的泛化性。
  - 消融实验验证了每个组件的必要性。
  - 不足之处：未报告多次重复实验的误差条，部分消融仅在一个数据集上做。
- **总体评价**：实验设计较全面，足以支撑结论；但统计严谨性略不足（无误差棒）。

### 6. 论文的主要结论与发现

- EDGE将蒸馏速度提升**18倍**，内存降低**16倍**，同时达到与SOTA方法相当甚至更优的检索性能。
- 在大型数据集CC3M上，EDGE是唯一可行的蒸馏方法，成功蒸馏了0.3‰比例的样本。
- 对比损失和多样性损失显著提升了生成样本的图像-文本对齐度和多样性。
- 文本合成策略能有效改善文本到图像检索性能，但需适量（CPI=2最优），过多标题反而因图像数量减少而损害性能。
- 方法具有较好的跨架构泛化能力，不依赖于特定的编码器架构。

### 7. 优点

- **高效性**：大大降低了时间和内存开销，使大规模多模态数据集蒸馏成为可能。
- **简洁性**：方法基于现有的Stable Diffusion，仅需微调少量参数，无需复杂的双水平优化。
- **可扩展性**：可直接用于百万级数据集CC3M，其他方法无法做到。
- **创新性**：将生成模型用于多模态蒸馏，并针对图像-文本对齐和多样性设计了专用损失。
- **实验充分**：涵盖3个数据集、多种指标、多组消融和跨架构评估，对比了主流方法。

### 8. 不足与局限

- **统计层面**：无误差分析（如重复实验的方差），结果的可靠性缺乏量化。
- **泛化性**：仅实验了Flickr30K、COCO、CC3M三个数据集，缺少更多领域（如医学、工业）的验证。
- **方法依赖**：严重依赖预训练扩散模型和MLLM的质量；若基础模型有偏见或缺陷，蒸馏结果可能受影响。
- **CPI选择**：仅探究了固定总数（500对）下的CPI影响，未研究在不同总样本量下的最佳配比。
- **碳足迹**：虽提到效率，但未整体估算训练碳排放。
- **理论不足**：缺乏对为何生成式蒸馏能得到更好性能的理论分析。

（完）
