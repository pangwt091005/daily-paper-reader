---
title: "CtrlSynth: Controllable Image Text Synthesis for Data-Efficient Multimodal Learning"
title_zh: "CtrlSynth: 可控图像文本合成实现数据高效的多模态学习"
authors: "Qingqing Cao, Mahyar Najibi, Sachin Mehta"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=z7lApwS4nV"
tags: ["query:nutritionk"]
score: 7.0
evidence: 可控图像-文本合成用于多模态学习的数据增强
tldr: CtrlSynth设计了一种可控图像-文本合成流水线，通过将图像视觉语义分解为基本元素并应用用户指定的控制策略，生成多样化的合成数据。该方法解决了多模态学习中数据集噪声大、长尾分布和多样性不足的问题，在多个基准上提升了CLIP等模型的鲁棒性，尤其适用于数据稀缺的食品营养分析领域。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-z7lapws4nv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1783, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z7lapws4nv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 769, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z7lapws4nv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1704, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z7lapws4nv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 673, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z7lapws4nv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1409, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z7lapws4nv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z7lapws4nv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1798, \"height\": 1044, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 723, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 687, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 700, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 756, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 620, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1430, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1382, \"height\": 1106, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 518, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 594, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1417, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1738, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z7lapws4nv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1423, \"height\": 420, \"label\": \"Table\"}]"
motivation: 现有的多模态数据集存在噪声、未对齐和长尾分布问题，而现有数据增强方法缺乏细粒度控制。
method: 提出可控图像-文本合成流水线，分解视觉语义并应用控制策略生成多样化的合成样本。
result: 在多个基准测试上提升了多模态模型的鲁棒性和数据效率。
conclusion: CtrlSynth为数据高效的多模态学习提供了一种灵活且可控的合成方法。
---

## Abstract
Pretraining robust vision or multimodal foundation models (e.g., CLIP) relies on large-scale datasets that may be noisy, potentially misaligned, and have long-tail distributions. Previous works have shown promising results in augmenting datasets by generating synthetic samples. However, they only support domain-specific ad hoc use cases (e.g., either image or text only, but not both), and are limited in data diversity due to a lack of fine-grained control over the synthesis process. In this paper, we design a controllable image-text synthesis pipeline, CtrlSynth, for data-efficient and robust multimodal learning. The key idea is to decompose the visual semantics of an image into basic elements, apply user-specified control policies (e.g., remove, add, or replace operations), and recompose them to synthesize images or texts. The decompose and recompose feature in CtrlSynth allows users to control data synthesis in a fine-grained manner by defining customized control policies to manipulate the basic elements. CtrlSynth leverages the capabilities of pretrained foundation models such as large language models or diffusion models to reason and recompose basic elements such that synthetic samples are natural and composed in diverse ways. CtrlSynth is a closed-loop, training-free, and modular framework, making it easy to support different pretrained models. With extensive experiments on 31 datasets spanning different vision and vision-language tasks, we show that CtrlSynth substantially improves zero-shot classification, image-text retrieval, and compositional reasoning performance of CLIP models.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：多模态预训练（如CLIP）依赖大规模数据集，但网络爬取数据存在噪声大、未对齐、长尾分布等问题。现有数据增强方法（如合成图像或文本）多为特定领域设计，缺乏细粒度控制，导致数据多样性不足。
- **动机**：希望构建一个灵活、可控的合成流水线，能够根据用户需求（如增强长尾类、避免敏感内容）生成高质量、多样化的图像-文本对，从而提升多模态模型的鲁棒性和数据效率。
- **整体含义**：CtrlSynth通过“分解-重组”视觉语义，利用预训练基础模型（LLM和扩散模型）实现可控合成，为多模态学习提供了一种数据高效的增强方案。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：将图像的视觉语义分解为基本元素（对象、属性、关系），然后应用用户定义的控制策略（如删除、添加、替换）并重组，生成新的图像或文本。
- **关键技术细节**：
  - **视觉标签模型（VTM）**：混合使用CatLIP（多标签分类）和Florence-large（详细描述）+ Qwen2-7B（提取标签），生成对象、属性、关系列表。
  - **文本控制器**：根据用户策略（如保留原文本语义、改变风格等）生成指令，指导LLM（Mistral-NeMo）合成新文本。
  - **图像控制器**：根据用户策略（如调整标签权重、指定风格）生成指令，指导扩散模型（SDXL）合成新图像。
  - **合成路径**：定义了多种路径（SP1：图像→文本；SP2：带原文本约束的文本；SP3：合成图像+文本；SP4：原文本→图像），用户可按需组合。
  - **闭环自过滤**：利用VTM检查合成文本是否包含足够比例的视觉标签，或检查合成图像的标签是否与原文本匹配，从而自动筛选低质量样本。
- **算法流程**（文字说明）：
  1. 输入图像（或文本）→ VTM提取标签。
  2. 文本控制器结合用户策略生成指令→ LLM根据标签和指令合成新文本。
  3. 图像控制器结合用户策略生成指令→ 扩散模型根据指令合成新图像。
  4. 可选：将合成图像再输入VTM，形成闭环过滤。

## 3. 实验设计

- **数据集与场景**：
  - **预训练数据集**：CC3M（2.8M图像-文本对）、CC12M（11.3M）、DataComp1B的子集（200M和400M）。
  - **零样本分类**：25个数据集，包括ImageNet及其变体（ImageNet-V2/A/O/R/S等）、VTAB基准（12个任务）。
  - **图像-文本检索**：COCO和Flickr30k，评估Recall@1。
  - **组合推理**：SugarCrepe基准（包含替换、交换等操作）。
  - **长尾任务**：ImageNet-LT、Places-LT（按头/中/尾类评估）。
- **基准方法**：CLIP基线、VeCLIP、LaCLIP（均为改进CLIP训练的文本重写方法）。
- **对比设置**：在相同迭代次数下训练，确保公平比较。

## 4. 资源与算力

- **GPU型号与数量**：CC3M预训练使用8个A100 GPU（40GB）；CC12M预训练使用32个A100 GPU；长尾微调使用1个A100 GPU。论文未明确给出每个实验的总训练时长或GPU小时数，但提到训练迭代次数（CC3M: 56,429次；CC12M: 55,429次）以及学习率调度等细节。

## 5. 实验数量与充分性

- **实验数量**：共涵盖31个数据集（25个分类、2个检索、1个组合推理、2个长尾），进行了多组对比实验和大量消融实验（不同合成路径、不同视觉标签类型、不同预训练模型、过滤阈值、混合比例等）。此外，还对比了VeCLIP、LaCLIP在3M/200M/400M规模上的表现。
- **充分性与公平性**：
  - 控制迭代次数相同，保证基线和方法看到相同样本量。
  - 消融实验全面，验证了各组件贡献（如视觉标签中关系的重要性、LLM选择的影响等）。
  - 但对比VeCLIP/LaCLIP时，由于训练框架、数据版本等差异，论文承认无法做到完全公平的“苹果对苹果”比较，但仍通过控制整体规模（3M/200M/400M）来近似。
  - 总体来看，实验量充足、设计合理、结论可信。

## 6. 主要结论与发现

- **性能提升显著**：
  - 零样本分类：在CC3M上平均提升7.7%，在CC12M上平均提升2.5%，在ImageNet-1K上分别提升5.1%和1.6%。
  - 检索任务：在CC3M上Recall@1平均提升23.4%，在CC12M上提升9.0%。
  - 组合推理（SugarCrepe）：在CC3M上平均提升4.5%，在CC12M上提升3.0%，尤其对属性替换和交换任务提升大。
  - 长尾任务：尾类准确率提升16~21%（ImageNet-LT和Places-LT），同时整体准确率提升3~5%。
- **数据效率更高**：达到ImageNet 20%准确率所需的训练迭代减少40%。
- **合成路径的影响**：混合合成文本和合成图像的路径（CtrlSynth-mix）效果最佳；单独合成文本（SP1）次之；单独合成图像（SP4）对组合推理无改善。
- **视觉标签的重要性**：包含关系的标签显著提升组合推理和分类性能；仅属性和对象时效果有限。
- **模型可替换性**：更强的LLM（Mistral-NeMo）优于较小模型（Qwen2-7B）；扩散模型（SDXL vs SD3M）差异不大。

## 7. 优点

- **模块化设计**：各组件（VTM、LLM、扩散模型）可独立替换，易于扩展。
- **无需额外训练**：完全利用预训练模型，适应性强。
- **可控性高**：通过控制策略（编辑标签、约束语义、指定风格）实现细粒度生成，可定制化。
- **闭环自过滤**：利用VTM自动筛选低质量样本，减少人工干预。
- **通用性强**：适用于分类、检索、组合推理、长尾等多种任务，且在多个数据集上验证。
- **数据效率提升**：显著减少训练所需迭代次数。

## 8. 不足与局限

- **实验覆盖**：仅针对CLIP模型进行验证，未测试其他多模态架构（如BLIP、ALBEF等）。
- **偏差风险**：合成数据可能继承原始数据集中的偏见，并可能放大伪影或敏感内容，论文未深入分析偏差传播。
- **应用限制**：依赖多个预训练模型（VTM、LLM、扩散模型），推理成本较高，不适合实时或计算资源受限场景。
- **未探索所有路径**：论文提到存在更多合成路径（如从合成数据再次合成），但未进行实验，潜力未完全挖掘。
- **对比公平性**：与VeCLIP/LaCLIP的对比因训练环境差异，难以严格控制，可能存在微小不公平。
- **过滤阈值较简单**：自过滤仅基于标签覆盖比例，未考虑更高级的语义对齐或生成质量。

（完）
