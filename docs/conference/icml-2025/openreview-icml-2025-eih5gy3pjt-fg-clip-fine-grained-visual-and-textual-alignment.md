---
title: "FG-CLIP: Fine-Grained Visual and Textual Alignment"
title_zh: "FG-CLIP: 细粒度视觉与文本对齐"
authors: "Chunyu Xie, Bin Wang, Fanjing Kong, Jincheng Li, Dawei Liang, Gengshen Zhang, Dawei Leng, Yuhui Yin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=eih5Gy3Pjt"
tags: ["query:nutritionk"]
score: 7.0
evidence: 细粒度视觉-文本对齐用于多模态识别
tldr: FG-CLIP针对CLIP在细粒度理解上的不足，提出利用大型多模态模型生成16亿长描述-图像对，并构建包含1200万图像和4000万区域框的高质量数据集，结合1000万困难负样本进行训练，显著提升了多模态任务的细粒度识别能力。该工作为食品图像等需要精细特征的任务提供了通用方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1763, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 401, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 396, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 397, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 583, \"height\": 2024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1617, \"height\": 1073, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1586, \"height\": 971, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eih5gy3pjt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1592, \"height\": 1136, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1646, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1525, \"height\": 1895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1495, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eih5gy3pjt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1382, \"height\": 252, \"label\": \"Table\"}]"
motivation: CLIP在处理细粒度理解任务时表现不足，因为其训练数据仅包含粗粒度的短描述。
method: 提出FG-CLIP，利用大模型生成长描述-图像对，构建区域级数据集，并加入困难负样本进行训练。
result: 在多个细粒度任务上取得了显著的性能提升。
conclusion: FG-CLIP通过细粒度对齐有效增强了多模态模型的理解能力。
---

## Abstract
Contrastive Language-Image Pre-training (CLIP) excels in multimodal tasks such as image-text retrieval and zero-shot classification but struggles with fine-grained understanding due to its focus on coarse-grained short captions. To address this, we propose Fine-Grained CLIP (FG-CLIP), which enhances fine-grained understanding through three key innovations. First, we leverage large multimodal models to generate 1.6 billion long caption-image pairs for capturing global-level semantic details. Second, a high-quality dataset is constructed with 12 million images and 40 million region-specific bounding boxes aligned with detailed captions to ensure precise, context-rich representations. Third, 10 million hard fine-grained negative samples are incorporated to improve the model's ability to distinguish subtle semantic differences. We construct a comprehensive dataset, termed FineHARD, by integrating high-quality region-specific annotations with challenging fine-grained negative samples. Corresponding training methods are meticulously designed for these data. Extensive experiments demonstrate that FG-CLIP outperforms the original CLIP and other state-of-the-art methods across various downstream tasks, including fine-grained understanding, open-vocabulary object detection, image-text retrieval, and general multimodal benchmarks. These results highlight FG-CLIP's effectiveness in capturing fine-grained image details and improving overall model performance. The data, code, and models are available at https://github.com/360CVGroup/FG-CLIP.

---

## 论文详细总结（自动生成）

基于提供的论文《FG-CLIP: Fine-Grained Visual and Textual Alignment》，以下是详细的中文总结：

---

### 1. 核心问题与整体含义（研究动机与背景）

- **核心问题**：传统的 CLIP 模型在处理细粒度视觉理解任务时表现不足，主要原因有两个：① 文本编码器仅支持 77 个 token，难以处理长且细致的描述；② CLIP 将整张图像与整个文本做全局对齐，缺乏区域级别的细粒度对齐能力。
- **研究动机**：为了提升 CLIP 在物体属性、关系、空间细节等方面的识别能力，使其能够胜任开放词汇目标检测、细粒度检索、多模态推理等下游任务。
- **整体含义**：本文提出 FG-CLIP，通过构建大规模、高质量的细粒度训练数据（长描述、区域描述、硬负样本）并设计对应的多阶段训练策略，显著提升了 CLIP 的细粒度对齐能力，为多模态模型的细粒度理解提供了通用框架。

---

### 2. 方法论：核心思想、关键技术细节

#### 核心思想
- 采用两阶段训练范式，先通过全局级长描述-图像对学习粗粒度-细粒度语义，再通过区域级对比学习和硬负样本学习进一步细化对齐能力。
- 核心创新：① 利用大模型（CogVLM2-19B）生成 16 亿对长描述-图像，扩展文本编码器支持最长 248 token；② 构建包含 1200 万图像、4000 万区域框的区域级数据集（FineHARD），每框配有详细描述；③ 引入 1000 万硬负样本（通过替换属性词生成）。

#### 关键技术细节
1. **全局对比学习**：保留短描述，同时加入长描述。文本位置编码进行线性插值（<=20 token 用原始位置编码，>20 则插值因子 4，最长 248 token）。损失函数为 InfoNCE（公式 2）。
2. **区域对比学习**：使用 RoIAlign 从图像编码器中提取区域特征（平均池化），文本则从全局描述中解析对应的短语/句子。区域级 InfoNCE 损失（公式 3）。
3. **硬负样本学习**：对每个区域，用 Llama-3.1-70B 生成 10 个负样本（仅修改属性词，保持物体名不变）。损失函数为多分类交叉熵形式（公式 4），使模型将区域特征推向正确描述，远离负样本。
4. **整体损失**：第二阶段总损失 L = L_global + α * L_regional + β * L_hard，其中 α=0.1，β=0.5。

#### 数据集构造（FineHARD）
- 基础：LAION-2B 图像 + GRIT 图像。
- 第一阶段：使用 CogVLM2-19B 为 LAION-2B 每张图生成长描述（短描述保留原始或另生成），得到 16 亿对。
- 第二阶段：基于 GRIT 图像，再生成图像级长描述 → 用 SpaCy 解析指代短语 → Yolo-World 检测生成边界框（置信度>0.4）→ 得到 1200 万图像、4000 万框区域描述。然后用 Llama-3.1-70B 生成 10 个硬负样本（替换属性），经人工检查 98.9%合格。

---

### 3. 实验设计

#### 数据集 / 场景与 Benchmark
- **细粒度区域理解**：FG-OVD benchmark（Bianchi et al.，2024），含 hard/medium/easy/trivial 四个难度等级。
- **边界框分类**：COCO-val2017、LVIS、Open Images（零样本，Top-1 准确率）。
- **开放词汇目标检测**：OV-COCO（AP novel_50、AP base_50、AP all_50）。
- **图像级检索**：长文本检索用 ShareGPT4V-1K 和 DCI（7,805 对）；短文本检索用 MSCOCO 5K 和 Flickr30K 1K。
- **零样本图像分类**：ImageNet-1K、ImageNet-v2。
- **通用多模态基准**：GQA、POPE、RefCOCO（val/testA/testB）、MMBench（EN/CN）。

#### 对比方法
- 基础：CLIP、EVA-CLIP、Long-CLIP、FineCLIP。
- 开放词汇检测：OV-RCNN、RegionCLIP、Detic、VLDet、RO-ViT、CFM-ViT、F-ViT、CLIPSelf 等。
- 多模态 LLM 基线：LLaVA-v1.5（使用 CLIP 与 FG-CLIP 对比）。

---

### 4. 资源与算力

- **数据处理算力**：使用 160 个 910B NPU 集群。第一阶段生成 16 亿长描述耗时 30 天；第二阶段构建 FineHARD 数据集耗时 7 天。
- **训练算力**：第一阶段：每 NPU 批次大小 384，使用 DeepSpeed Zero-2、Bfloat16，训练 1 个 epoch；第二阶段：每 GPU 批次大小 512，DeepSpeed Zero-2 + CUDA TF32 + Bfloat16，训练 1 个 epoch。论文未明确给出 GPU/NPU 总数量或具体型号，仅说明使用了 160×910B NPU 集群进行数据处理，训练阶段可能复用该集群但未详述。

---

### 5. 实验数量与充分性

- **实验数量**：共进行了 6 大类实验（细粒度理解、边界框分类、开放词汇检测、图像级检索/分类、多模态 LLM 基准、消融研究），每个大类下又有多个子数据集。共报告了 9 张表格（包括附录）。
- **消融实验**：逐步添加全局对比、区域对比、硬负样本学习，验证了各组件的贡献。还在相同数据集上对比了 FineCLIP 与 FG-CLIP（表 8），证明了模型和数据的有效性。
- **公平性**：与其他方法使用相同的骨干网络（ViT-B/16、ViT-L/14）和相同的测试协议，比较客观。开放词汇检测中统一使用 F-ViT 作为检测框架，仅替换视觉编码器，控制变量。
- **充分性**：覆盖了细粒度、粗粒度、零样本、多模态 LLM 等多个维度，实验设计完整、结果详实。

---

### 6. 主要结论与发现

- FG-CLIP 在所有细粒度相关基准上显著优于原生 CLIP 及其他 SOTA 方法，尤其在 FG-OVD 的 hard 子集上准确率从 FineCLIP 的 26.8% 提升至 46.1%（ViT-B/16）。
- 在开放词汇目标检测（OV-COCO）中，AP novel_50 达到 41.2%（ViT-L/14），相比基线有大幅提升。
- 在长/短文本检索、零样本分类上保持或超越了已有方法，未因细粒度增强而牺牲全局性能。
- 作为 LLaVA 的视觉编码器，在 GQA、POPE、RefCOCO 上均有提升，验证了细粒度对齐对多模态 LLM 的益处。
- 消融表明：长描述数据（全局）和区域对比学习显著提升区域理解，硬负样本学习在 FG-OVD 难度较大子集上带来决定性提升。

---

### 7. 优点

- **大规模高质量数据构造**：首次使用 16 亿对长描述-图像，配合 4000 万区域框和 1000 万硬负样本，规模和质量均超越过往工作。
- **两阶段训练策略**：第二阶段统一全局、区域、硬负样本三种损失，实现了多层级对齐的协同优化。
- **显著的细粒度性能提升**：在最具挑战性的 hard 子集上提升接近 20 个点，证明了方法的有效性。
- **开源与可复现**：代码、模型、数据集（FineHARD）全部公开，便于后续研究。
- **通用性**：不仅提升纯 CLIP 任务，还改善了下游多模态 LLM 的幻觉问题和定位能力。

---

### 8. 不足与局限

- **数据噪声**：长描述和区域描述由 CogVLM2-19B 自动生成，硬负样本由 Llama-3.1 生成，虽然质检合格率 98.9%，但仍存在少量噪声（1.1%），可能影响模型稳健性。
- **计算资源需求巨大**：使用 160 个 910B NPU 集群进行数据处理和训练，普通研究组难以复现。
- **实验覆盖有限**：未在视频、医疗、遥感等特殊领域评估；未与更近期的模型（如 SigLIP、BLIP-2 等）对比。
- **语言局限于英语**：数据集和模型主要针对英语，跨语言泛化能力未验证。
- **文本长度限制**：虽然扩展至 248 token，但对于极其长的描述（如文档级）仍可能不足。
- **区域标注依赖预训练检测器**：Yolo-World 可能引入框的定位误差，从而影响区域对齐。

---

（完）
