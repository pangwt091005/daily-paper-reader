---
title: "LMFusion: Adapting Pretrained Language Models for Multimodal Generation"
title_zh: LMFusion：适配预训练语言模型用于多模态生成
authors: "Weijia Shi, Xiaochuang Han, Chunting Zhou, Weixin Liang, Xi Victoria Lin, Luke Zettlemoyer, LILI YU"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Kc1WTxZbrP"
tags: ["query:nutritionk"]
score: 4.0
evidence: 文本与图像的多模态生成框架
tldr: 该论文解决纯文本大语言模型缺乏多模态生成能力的问题，提出LMFusion框架，在保持文本模块不变的同时，引入并行的扩散模块处理图像，通过共享自注意力层实现跨模态交互。训练时文本模块冻结仅训练图像模块，从而高效实现图文交错生成，为食品营养预测中的视觉-语言联合生成任务提供基础架构。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1221, \"height\": 860, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kc1wtxzbrp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 298, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kc1wtxzbrp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1463, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kc1wtxzbrp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1425, \"height\": 452, \"label\": \"Table\"}]"
motivation: 现有语言模型无法处理图像，需要扩展其多模态能力。
method: 在LLM中增加并行的扩散图像模块，共享自注意力层进行跨模态交互。
result: 在图文生成任务上，LMFusion保持了文本性能同时获得了图像生成能力。
conclusion: LMFusion是一种轻量级将语言模型扩展为多模态生成模型的方法。
---

## Abstract
We present LMFusion, a framework for empowering pretrained text-only large language models (LLMs) with multimodal generative capabilities, enabling them to understand and generate both text and images in arbitrary sequences. LMFusion leverages existing Llama-3's weights for processing texts autoregressively while introducing additional and parallel transformer modules for processing images with diffusion. During training, the data from each modality is routed to its dedicated modules: modality-specific feedforward layers, query-key-value projections, and normalization layers process each modality independently, while the shared self-attention layers allow interactions across text and image features. By freezing the text-specific modules and only training the image-specific modules, LMFusion preserves the language capabilities of text-only LLMs while developing strong visual understanding and generation abilities. Compared to methods that pretrain multimodal generative models from scratch, our experiments demonstrate that, LMFusion improves image understanding by 20% and image generation by 3.6% using only 50% of the FLOPs while maintaining Llama-3's language capabilities. We also demonstrate that this framework can adapt existing vision-language models with multimodal generation ability. Overall, this framework not only leverages existing computational investments in text-only LLMs but also enables the parallel development of language and vision capabilities, presenting a promising direction for efficient multimodal model development.

---

## 论文详细总结（自动生成）

# LMFusion: 适配预训练语言模型用于多模态生成 —— 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：如何将纯文本大语言模型（如 Llama-3）高效扩展为能够理解和生成任意序列文本与图像的多模态模型，同时**完全保留其原有的语言能力**，避免因多模态微调导致的灾难性遗忘。
- **背景**：现有统一多模态模型（如 Transfusion、Chameleon）通常从头训练，计算成本极高（例如 Llama-3 需超过 15 万亿 token 的训练）。而直接将预训练语言模型在图文数据上微调会导致语言能力大幅下降。因此，需要一种既能利用已有文本模型权重、又能独立学习视觉能力的框架。

## 2. 方法论

### 核心思想
- **模态分离 + 参数冻结**：基于 Transfusion 架构（自回归文本 + 扩散图像），但引入**模态特定的并行 Transformer 模块**：文本专用模块（QKV、FFN、归一化层）与图像专用模块。所有模块从 Llama-3 初始化，训练时**完全冻结文本模块**，仅训练图像模块，从而在保持语言能力的同时学习视觉理解与生成。

### 关键技术细节
- **架构**：每个 Transformer 层包含：
  - 文本输入 → 专用 QKV 投影 → 文本专用 FFN
  - 图像输入（经 VAE 编码 + U-Net 下采样）→ 专用 QKV 投影 → 图像专用 FFN
  - **共享自注意力层**：将文本和图像的 Q、K、V 拼接后一起计算注意力，允许跨模态交互。注意力掩码为文本使用因果掩码、图像使用双向掩码。
- **损失函数**：结合语言建模损失（文本的下一个 token 预测）和 DDPM 扩散损失（预测噪声），超参数 λ 平衡两者。与 Transfusion 相同。
- **训练策略**：解耦学习率：文本模块学习率 ηtext = 0（冻结），图像模块学习率 ηimage = 1×10⁻⁴（AdamW，余弦衰减，4000 步 warmup）。
- **图像表征**：使用预训练的 VAE 将 256×256 图像压缩为 32×32×8 张量，经 2 块 U-Net 下采样器得到 256 个 patch（token）。反向上采样同理。

### 公式（文字说明）
- 文本语言建模：计算交叉熵损失预测每个下一个 token。
- 图像扩散：在前向过程添加高斯噪声，模型学习逆向预测噪声；损失为预测噪声与真实噪声的均方误差。
- 总损失 = LLM + λ·LDDPM。

## 3. 实验设计

### 数据集
- **训练数据**：380M 张 Shutterstock 图像-描述对（与 Transfusion 相同），图像中心裁剪并缩放到 256×256。80% 时间将描述置于图像之前（强调文本条件图像生成），20% 相反。
- **评估基准**：
  - 语言能力：HellaSwag、SIQA、WinoGrande（准确率）
  - 图像理解：MS-COCO 测试集上的 CIDEr 分数（生成描述）
  - 图像生成：MS-COCO 验证集 30K 随机提示，FID 和 CLIP 分数（无 CFG 和有 CFG=1.55/1.6）

### 对比方法
- **主要基线**：Transfusion 7B（从头训练）；从 Llama-3 初始化的 Transfusion（无模态分离的稠密模型）。
- **扩展实验**：LLaVAFusion（基于 LLaVA-NeXT 8B），对比 EMU-3、Show-O、Janus、Chameleon、MetaMorph、Transfusion 等。
- **消融实验**：对比三种架构设计（稠密无分离、浅层分离/仅 FFN 分离、深层分离/本文方法），以及不同学习率比例（ηtext/ηimage ∈ {0, 0.1, 1}）。

## 4. 资源与算力

- **主要实验**：训练 LMFusion（基于 Llama-3 8B）使用 **128 块 H100 GPU**，训练 **约 4 天**（处理 0.25T 图像 token，无文本 token）。
- **消融实验**：小规模变体训练 250K 步，批次大小 250K token，序列长度 4096，使用 0.03T 文本 + 0.03T 图文 token（具体 GPU 数量未单独说明，与主实验环境一致）。
- 由于冻结文本模块，无需像 Transfusion 那样同时处理文本数据，**总 FLOPs 约为 Transfusion 的 50%**。

## 5. 实验数量与充分性

- **主要实验**：报告了语言、理解、生成三个类别共约 7 个指标（HellaSwag/SIQA/WinoGrande/CIDEr/FID/CLIP，有/无 CFG 的 FID/CLIP）。
- **消融实验**：系统地比较了不同分离程度（3 种） × 不同学习率比例（3 种），并提供了训练过程中的曲线（图 4、图 5），展示了语言和图像性能随步数的变化。
- **扩展实验**：LLaVAFusion 在 4 个理解基准 + 生成 FID 上对比了 7 个近期多模态模型。
- **充分性评价**：
  - ✅ 多任务覆盖：语言、理解、生成全部评估。
  - ✅ 消融设计清晰：分离程度、学习率控制变量。
  - ✅ 训练过程监控：报告了训练过程中的 CIDEr、CLIP、FID、HellaSwag 曲线，有助于分析动态行为。
  - ⚠️ 缺陷：未报告标准误差或置信区间（仅一次运行，但连续 checkpoints 显示趋势）；MS-COCO 单数据集评估图像理解与生成；未在更多挑战性图文任务（如视觉问答 benchmark MMMU、ChartQA 等）上评估 LMFusion 主模型（仅 LLaVAFusion 评了这些）；语言评估仅使用三个常识推理基准，未覆盖更多样化的 NLP 任务。

## 6. 主要结论与发现

1. **LMFusion 在保持 Llama-3 文本性能不变的前提下**，图像理解（CIDEr）提升 20%，图像生成（FID/CLIP）提升 3.6%，且仅使用 Transfusion 一半的 FLOPs。
2. **框架有效性**：不仅可扩展纯文本 LLM，也能将现有视觉语言模型（如 LLaVA）转化为可生成图像的多模态模型（LLaVAFusion 在多项基准上取得有竞争力结果）。
3. **消融关键发现**：
   - 直接微调稠密预训练 LLM（无模态分离）会导致语言能力显著下降（HellaSwag 降低 15% 以上，且无法完全恢复）。
   - **深层分离**（FFN + 注意力）优于浅层分离（仅 FFN）和无分离，在图像任务上表现更好。
   - 冻结文本模块（学习率比例=0）是保持语言能力的最有效措施，且不会损害图像学习。

## 7. 优点

- **高效复用**：利用现有 Llama-3 权重，避免从头训练语言部分，大幅降低计算成本和数据需求。
- **语言能力无损**：冻结文本模块的策略简单有效，实现语言性能的完美保留。
- **模块化设计**：文本与图像模块可独立开发、训练，易于扩展（如替换更先进的图像生成骨干）。
- **通用性**：框架适用于不同基础模型（语言模型或视觉语言模型），实验证明可成功适配 LLaVA 系列。
- **清晰的消融**：通过控制变量实验揭示了关键设计决策（分离程度、学习率比例）的影响，方法论可靠。

## 8. 不足与局限

- **计算成本依然较高**：尽管减半 FLOPs，仍需 128 块 H100 训练 4 天；图像模块仍需从零训练（0.27B U-Net 参数），未来可探索重用预训练图像生成组件（论文自述）。
- **评估局限性**：
  - 图像理解仅用 CIDEr 单一指标，且仅在 MS-COCO 上评估（缺乏多样性和难度区分）。
  - 图像生成仅用 FID/CLIP，未进行人类评估或更细致的质量和多样性分析。
  - 语言评估仅三个常识推理基准，未能全面衡量通用语言能力（如问答、翻译、推理等）。
  - 未在更多标准多模态基准（如 MMMU、ChartQA、RealWorldQA）上评估 LMFusion 主模型（仅在 LLaVAFusion 消融中进行了这些指标的对比）。
- **潜在偏差风险**：训练数据仅来自 Shutterstock（一种图像-描述数据集），风格和内容可能受限；未讨论数据公平性或模型偏见问题。
- **应用限制**：图像生成分辨率固定为 256×256，未探索更高分辨率或视频生成；文本与图像交互的复杂性（如长图文交错）未深入分析。
- **未开源完整实现**：代码将开源，但当前论文中未提供可复现的代码或模型权重细节（如是否使用 deepspeed、混合精度等）。

（完）
