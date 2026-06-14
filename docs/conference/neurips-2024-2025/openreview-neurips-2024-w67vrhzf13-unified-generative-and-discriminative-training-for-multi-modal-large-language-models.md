---
title: Unified Generative and Discriminative Training for Multi-modal Large Language Models
title_zh: 多模态大语言模型的统一生成与判别训练
authors: "Wei Chow, Juncheng Li, Qifan Yu, Kaihang Pan, Hao Fei, Zhiqi Ge, Shuai Yang, Siliang Tang, Hanwang Zhang, Qianru Sun"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=w67vRHZF13"
tags: ["query:nutritionk"]
score: 5.0
evidence: 统一生成与判别训练的多模态大语言模型
tldr: 多模态大语言模型存在生成幻觉和判别能力弱的问题，而CLIP类模型缺乏复杂场景理解。本文提出统一训练框架，通过结构诱导策略同时优化生成和判别目标。实验表明，该方法在VQA和分类任务上均显著提升，尤其在需要细粒度语义区分的场景表现突出。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1423, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1325, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1424, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1312, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1434, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 139, \"height\": 107, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 137, \"height\": 109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 65, \"height\": 81, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1438, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1441, \"height\": 2081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1442, \"height\": 1362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 311, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 176, \"height\": 134, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 178, \"height\": 140, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 137, \"height\": 138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 135, \"height\": 136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 140, \"height\": 141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1280, \"height\": 190, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 138, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 133, \"height\": 134, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 81, \"height\": 88, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 76, \"height\": 80, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 672, \"height\": 143, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 518, \"height\": 139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 137, \"height\": 136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 190, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 194, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 196, \"height\": 129, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 169, \"height\": 122, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 110, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1431, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 152, \"height\": 135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 225, \"height\": 131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 198, \"height\": 133, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1256, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 235, \"height\": 131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 101, \"height\": 132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 92, \"height\": 132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 105, \"height\": 130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-w67vrhzf13/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1261, \"height\": 199, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1398, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 886, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 399, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 514, \"height\": 380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 366, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 461, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 727, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 798, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1404, \"height\": 519, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-w67vrhzf13/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 653, \"height\": 384, \"label\": \"Table\"}]"
motivation: 生成式MLLM有幻觉和弱判别，判别式模型缺乏复杂场景理解。
method: 提出结构诱导训练策略，结合生成和判别任务的目标进行联合优化。
result: 在VQA和分类任务上提升性能，减少幻觉并增强细粒度区分。
conclusion: 统一生成与判别训练为MLLM提供了更全面的学习范式。
---

## Abstract
In recent times, Vision-Language Models (VLMs) have been trained under two predominant paradigms. Generative training has enabled Multimodal Large Language Models (MLLMs) to tackle various complex tasks, yet issues such as hallucinations and weak object discrimination persist. Discriminative training, exemplified by models like CLIP, excels in zero-shot image-text classification and retrieval, yet struggles with complex scenarios requiring fine-grained semantic differentiation. This paper addresses these challenges by proposing a unified approach that integrates the strengths of both paradigms. Considering interleaved image-text sequences as the general format of input samples, we introduce a structure-induced training strategy that imposes semantic relationships between input samples and the MLLM’s hidden state. This approach enhances the MLLM’s ability to capture global semantics and distinguish fine-grained semantics. By leveraging dynamic sequence alignment within the Dynamic Time Warping framework and integrating a novel kernel for fine-grained semantic differentiation, our method effectively balances generative and discriminative tasks. Extensive experiments demonstrate the effectiveness of our approach, achieving state-of-the-art results in multiple generative tasks, especially those requiring cognitive and discrimination abilities. Additionally, our method surpasses discriminative benchmarks in interleaved and fine-grained retrieval tasks. By employing a retrieval-augmented generation strategy, our approach further enhances performance in some generative tasks within one model, offering a promising direction for future research in vision-language modeling.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）

- 当前多模态大语言模型（MLLMs）主要依赖生成式训练，虽能处理复杂任务，但存在幻觉（hallucination）和弱目标判别能力。
- 判别式模型（如CLIP）在零样本图像-文本分类和检索上表现出色，但难以处理需要细粒度语义区分的复杂场景（如交错图文检索）。
- 两种范式割裂，缺乏协同。本文旨在统一生成与判别训练，让MLLMs同时具备强大的生成能力和精确的判别能力，特别是捕获全局语义和区分细粒度细节。

#### 2. 方法论：核心思想、关键技术细节

- **核心思想**：提出 **Sugar**（Structure-induced approach to unify generative and discriminative paradigms）。将交错图像-文本序列作为通用输入格式，通过显式施加样本间的语义关系作为结构约束到MLLM的隐藏状态上，迫使模型更好地捕获全局语义和细粒度细节。
- **关键技术细节**：
  - **动态序列对齐（Dynamic Sequence Alignment）**：将两个交错序列的相似度计算建模为动态时间规整（DTW）框架下的全局对齐核问题。使用全局对齐核（Global Alignment Kernel, GAK）计算序列相似度矩阵，其定义：  
    \( K(\mathbf{x},\mathbf{y}) = \sum_{\pi \in A(\mathbf{x},\mathbf{y})} \prod_{i=1}^{|\pi|} e^{-\phi_\sigma} \)，其中对齐路径 \(\pi\) 和自定义距离 \(\phi_\sigma\) 保证核正定性。
  - **三重核（Triple Kernel, TK）**：为区分细粒度语义，提出结合多个预训练判别模型（DINOv2、CLIP ViT-L/14、BGE-base）的核，对图像和文本分别采用不同嵌入组合，并设计条件正定核公式。
  - **损失函数**：总损失 \(L = L_g + \alpha L_d\)，其中 \(L_g\) 为生成式自回归损失，\(L_d\) 为判别式损失（用MSE对齐模型隐藏状态得到的相似度矩阵与输入序列真实相似度矩阵）。
  - **实现细节**：选择MLLM隐藏状态中最后一个token（对图像使用平均池化）作为序列表示，经MLP映射后用于相似度计算。训练时无需预定义正负例，通过动态对齐自动生成标签。

#### 3. 实验设计

- **数据集与场景**：
  - **生成基准**：11个常用视觉-语言基准（VQA-v2、GQA、VizWiz、ScienceQA-IMG、TextVQA、POPE、MME、MMBench、LLaVA-Bench、MM-Vet）。
  - **复杂理解**：DEMON基准（7大类共29子任务），评估交错图文指令理解能力。
  - **判别基准**：
    - 图像-文本检索：MSCOCO（标准检索）。
    - 交错检索：VIST（Visual Storytelling，基于故事序列检索图像）。
    - 细粒度检索：Winoground（视语言组合推理）。
  - **检索增强生成（RAG）**：在VizWiz和ScienceQA上测试，使用held-in数据作为知识库。
- **对比方法**：VILA、LLaVA-1.5、BLIP-2、InstructBLIP、Qwen-VL、FROMAGe、CLIP变体等。

#### 4. 资源与算力

- 训练在 **8×A800 GPU** 上运行约 **12小时**。
- 使用 LoRA 微调（rank=128, α=256），AdamW 优化器，余弦学习率，最大学习率 1e-4，预热比例 0.03。
- 初始化自 VILA 模型。

#### 5. 实验数量与充分性

- 实验非常充分：
  - 在11个生成基准上对比8+种方法，取得多项SOTA。
  - 在DEMON 29任务上对比6种方法，6/7类别领先。
  - 在3类判别任务（MSCOCO、VIST、Winoground）上与FROMAGe、CLIP等对比，表现优异。
  - 进行了RAG实验（两个任务）和详细的消融实验（5项：去除生成数据、去除判别数据、去除GAK、去除TK、去除平均池化）。
- 实验设置客观公平：使用统一评估协议、公开数据集，消融实验揭示了各组件贡献。

#### 6. 主要结论与发现

- 统一生成与判别训练能产生协同增益：生成能力（特别是细粒度、认知、幻觉检测）提升，判别能力（尤其是交错和细粒度检索）达到SOTA。
- 动态序列对齐（GAK）有效帮助模型捕获全局语义；三重核（TK）显著增强细粒度语义区分。
- 单个模型可直接实现检索增强生成，优于使用外部检索器（如CLIP），避免兼容性和优化问题。
- 生成数据不足会降低判别性能，反之亦然，两者相互促进。

#### 7. 优点

- **方法创新**：首次将动态时间规整和对齐核引入多模态大模型训练，巧妙利用隐藏状态进行序列相似度学习。
- **三重核设计**：融合多种预训练判别模型的优势，无需额外参数学习，有效提升细粒度区分。
- **实验全面**：覆盖生成、判别、复杂理解、RAG等多场景，消融验证充分。
- **实用价值**：单个模型同时完成生成和检索，简化部署，且RAG可进一步提升生成质量。

#### 8. 不足与局限

- **继承缺陷**：可能继承底层模型（Vicuna、CLIP、DINOv2）的幻觉、偏见问题。
- **数据风险**：训练数据可能包含不匹配的图文对，影响训练稳定性。
- **计算开销**：动态对齐算法复杂度为O(m n d²)，对长序列可能效率较低。
- **泛化性**：方法基于特定MLLM（VILA）和特定预训练模型，推广到其他架构或更大规模模型需验证。
- **应用限制**：虽然展示了RAG效果，但仅在少数任务上测试，实际部署时仍可能面临知识库更新和领域适应问题。
- **未讨论公平性**：论文未分析模型在不同群体或敏感属性上的表现差异。

（完）
