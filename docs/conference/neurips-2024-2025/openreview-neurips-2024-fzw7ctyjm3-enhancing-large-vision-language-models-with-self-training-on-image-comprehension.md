---
title: Enhancing Large Vision Language Models with Self-Training on Image Comprehension
title_zh: 通过图像理解自训练增强大型视觉语言模型
authors: "Yihe Deng, Pan Lu, Fan Yin, Ziniu Hu, Sheng Shen, Quanquan Gu, James Zou, Kai-Wei Chang, Wei Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=FZW7Ctyjm3"
tags: ["query:nutritionk"]
score: 4.0
evidence: 视觉语言模型图像理解自训练方法
tldr: 该论文针对视觉语言模型高质量标注数据获取昂贵的问题，提出自训练图像理解方法STIC，让模型利用自身生成的数据来增强视觉感知和推理能力。在多个视觉语言任务上，STIC以无标签数据方式提升了模型性能，为食品图像识别与营养预测等需要大规模视觉-语言对齐的任务提供了低成本数据增强思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 826, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 417, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 734, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 421, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 573, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 408, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 413, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 387, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 575, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1191, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 434, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-fzw7ctyjm3/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1436, \"height\": 986, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 795, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 803, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 708, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 708, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-fzw7ctyjm3/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1203, \"height\": 257, \"label\": \"Table\"}]"
motivation: 高质量视觉-语言数据获取成本高，需减少对人工标注的依赖。
method: 提出STIC，让模型自我生成数据并用于图像理解的自训练。
result: 在多个视觉语言基准测试上，无需额外标注即提升了模型性能。
conclusion: STIC是一种有效的视觉语言模型自训练范式，可降低数据成本。
---

## Abstract
Large vision language models (LVLMs) integrate large language models (LLMs) with pre-trained vision encoders, thereby activating the perception capability of the model to understand image inputs for different queries and conduct subsequent reasoning. Improving this capability requires high-quality vision-language data, which is costly and labor-intensive to acquire. Self-training approaches have been effective in single-modal settings to alleviate the need for labeled data by leveraging model's own generation. However, effective self-training remains a challenge regarding the unique visual perception and reasoning capability of LVLMs. To address this, we introduce **S**elf-**T**raining on **I**mage **C**omprehension (**STIC**), which emphasizes a self-training approach specifically for image comprehension. First, the model self-constructs a preference dataset for image descriptions using unlabeled images. Preferred responses are generated through a step-by-step prompt, while dis-preferred responses are generated from either corrupted images or misleading prompts. To further self-improve reasoning on the extracted visual information, we let the model reuse a small portion of existing instruction-tuning data and append its self-generated image descriptions to the prompts. We validate the effectiveness of STIC across seven different benchmarks, demonstrating substantial performance gains of 4.0% on average while using 70% less supervised fine-tuning data than the current method. Further studies dive into various components of STIC and highlight its potential to leverage vast quantities of unlabeled images for self-training.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

大型视觉语言模型（LVLMs）通过将大型语言模型（LLMs）与预训练视觉编码器结合，实现对图像输入的理解和后续推理。然而，提升这种能力需要高质量的视觉-语言数据，而这类数据的获取成本高昂且劳动密集。现有的方法常依赖GPT-4V等高级模型生成标注数据，但并未显著降低成本（例如生成6k图像描述需约200美元）。因此，迫切需要一种经济有效的方法来收集微调数据，以进一步增强LVLMs。单模态场景中的自训练方法已被证明能有效缓解对标注数据的依赖，但针对LVLMs独特的视觉感知和推理能力，有效的自训练仍具有挑战。本文提出的**STIC**（Self-Training on Image Comprehension）正是为了解决这一问题，通过利用无标签图像自我构建偏好数据，实现模型对图像理解能力的自我提升，从而降低对人工标注或高级教师模型的依赖。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

STIC是一个两阶段的自训练算法，专注于增强LVLMs的图像理解能力。

### 第一阶段：图像理解自训练（Image Comprehension Self-Training）
- **核心思想**：模型利用无标签图像自我构建偏好数据集（preference dataset），用于图像描述任务。
- **偏好数据构建**：
  - **首选响应（Preferred response）**：使用精心设计的逐步提示（step-by-step prompt）引导模型生成详细的图像描述。提示涵盖主要主体、场景、氛围、色彩、构图等。
  - **非首选响应（Dispreferred response）**：通过两种方式生成：
    1. **不良提示（Bad prompting）**：使用设计为诱导幻觉的提示（如“描述图像中可能存在但实际不存在的物体”），使模型产生不准确的描述。
    2. **图像损坏（Image corruption）**：对图像施加颜色抖动或降低分辨率，然后使用正常提示让模型生成描述。
- **训练损失**：采用带正则化的直接偏好优化（DPO）损失，额外增加一个项α log pθ(y_w|x)来强调首选响应，损失函数为：
  \[
  L(\theta, \theta_{\text{ref}}) = \mathbb{E}_{(x,y_w,y_l)\sim S} \left[ \ell\left( \lambda \log \frac{p_\theta(y_w|x)}{p_{\theta_{\text{ref}}}(y_w|x)} - \lambda \log \frac{p_\theta(y_l|x)}{p_{\theta_{\text{ref}}}(y_l|x)} \right) - \alpha \log p_\theta(y_w|x) \right]
  \]
  其中ℓ(t) = log(1+exp(-t))，θ_ref为参考模型（即初始模型），λ和α为超参数。

### 第二阶段：描述注入微调（Description-Infused Fine-Tuning）
- **核心思想**：让模型利用自身生成的图像描述来增强对指令的推理能力。
- **操作**：从模型已有的指令微调数据中随机选取一小部分（例如5k条），将每个样本的原始指令之前拼接上模型自己生成的图像描述（如“Image description: {模型生成的描述} <原始指令>”），保持原始答案不变。然后对整个LVLM进行一个epoch的微调。
- **推理时可选的“描述并回答”（Describe and Respond, DaR）**：在回答下游查询之前，先让模型生成图像描述，然后将描述与原始问题拼接，再生成最终答案。

整个流程无需任何预标注的图像信息，完全依赖模型自身生成的数据。算法流程详见论文Algorithm 1和2。

## 3. 实验设计

### 使用的数据集/场景
- **无标签图像**：用于构建偏好数据，采用MSCOCO数据集（train2014分片），随机采样6k张图像（后续实验扩展到12k）。
- **指令微调数据**：第二阶段使用LLaVA已有的SFT数据，随机选取5k条用于描述注入微调。
- **评估基准（7个）**：
  - **ScienceQA**：科学问答（推理与知识）。
  - **TextVQA**：包含文本丰富图像的视觉问答（OCR能力）。
  - **ChartQA**：图表问答（逻辑推理）。
  - **LLaVA-Bench**：综合对话与理解能力评估（使用GPT-4评估）。
  - **MMBench**：多模态能力全面评估（涵盖6个能力维度）。
  - **MM-Vet**：综合能力评估（6个任务类型）。
  - **MathVista**：数学推理（视觉上下文中的数学问题）。

### 对比方法
- **基线模型**：LLaVA-v1.6（Mistral-7B）作为主要基座，也使用了LLaVA-v1.5（Vicuna-7B）与同期工作POVID对比。
- **其他对比**：InstructBLIP (7B)、mPLUG-OWL2 (7B) 等作为参考。
- **STIC变体**：包括是否使用DaR、是否去除负面样本（仅SFT）、不同数据源（COCO vs VFLAN）、不同模型规模（13B）等。

### 评估方式
使用LLaVA官方评估脚本进行公平比较，主要指标为准确率（部分基准如LLaVA-Bench使用GPT-4评分）。

## 4. 资源与算力

论文附录B明确说明了计算资源：
- **GPU型号**：NVIDIA RTX A6000 GPU集群。
- **训练时长**：对于LLaVA-v1.5 (7B) 和 LLaVA-v1.6 (7B) 的整个自训练过程（使用6k图像+5k指令数据），在4张GPU上约需6小时。
- **评估时长**：各基准评估通常需2至8小时，取决于测试集大小。
- **微调细节**：使用LoRA（lora_r=128, lora_alpha=256, target=all），学习率等超参数见附录表6。

## 5. 实验数量与充分性

论文进行了多组实验，涵盖：
- **主实验结果**：在7个基准上对比STIC与原始LLaVA-v1.6和v1.5（表1），展示平均提升4.0%。
- **消融实验**：
  - 验证“描述并回答”（DaR）的有效性（表2）。
  - 展示两阶段渐进提升效果（图5）。
  - 分析负面样本的作用（表3）：去除负面样本后性能下降2.5%。
  - 缩放律实验：数据量从6k增至12k时LLaVA-Bench提升从1.9%增至3.1%（图6）。
  - 图像分布相关性：t-SNE可视化分析MSCOCO与各基准图像分布的关系（图7）。
  - 多样性实验：使用VFLAN数据集（191种视觉任务）替代COCO，性能进一步提升（表4）。
  - 模型规模扩展：在LLaVA-v1.6 (13B) 上也取得提升（表5）。
  - 提示质量调查：对比不同提示对DaR的影响（附录表9）。
- **定性示例**：多个直观案例展示STIC改善的响应（图1,8,12,13）。

**充分性评估**：实验覆盖全面，从多个维度验证了STIC的有效性，消融实验设计合理，对比公平。但缺乏多次重复运行（除LLaVA-Bench外）的误差棒，可能由于解码策略和计算成本限制，但总体结论稳健。

## 6. 主要结论与发现

1. **STIC显著提升LVLMs性能**：在7个视觉语言基准上平均提升4.0%（LLaVA-v1.6），最高提升6.4%（ScienceQA）。
2. **自训练数据无需标注**：仅使用无标签的MSCOCO图像构建偏好数据，且第二阶段仅复用原有SFT数据的一小部分（70%更少的监督数据）。
3. **偏好数据中的负面样本至关重要**：去除负面样本后性能下降，表明DPO训练中负面数据对对齐质量的关键作用。
4. **缩放潜力大**：增加无标签图像数量可带来更大增益，表明STIC可以充分利用海量无标签数据。
5. **图像分布匹配影响性能提升**：t-SNE分析显示，训练图像与下游任务图像分布相似度越高，提升越显著；但即使分布不同（如ChartQA），STIC仍能通过增强基础图像理解带来收益。
6. **可扩展至更大模型**：在13B模型上同样有效，验证了方法的通用性。
7. **“描述并回答”策略**：结合STIC微调后，DaR能进一步带来平均1.1%的提升，单独应用于基线可能效果不稳定。

## 7. 优点

- **完全无监督的数据构建**：无需人工标注或API调用，仅利用无标签图像和模型自身生成，成本极低。
- **两阶段设计合理**：第一阶段专注于提升图像感知，第二阶段注入描述增强推理，协同增效。
- **广泛的实验验证**：在7个不同领域的基准上均取得一致提升，涵盖自然图像、图表、文字密集图像、数学推理等，通用性强。
- **丰富的消融分析**：深入探讨了负面样本、数据量、图像分布、提示设计、模型规模等因素，提供了扎实的分析依据。
- **实际可用性强**：使用LoRA微调，计算需求适中，且代码和数据已开源，便于复现和扩展。
- **清晰的动机与创新**：针对LVLMs数据瓶颈提出自训练方案，与现有依赖GPT-4V或标注数据的方法形成鲜明对比。

## 8. 不足与局限

- **对特定任务提升有限**：在MathVista上提升仅2.4%，可能由于图像类型多样且超出纯图像理解范畴，需更针对性的数据。
- **偏好数据构建策略较简单**：仅基于提示和图像损坏区分好坏，对于需要细微差异的场景可能不够。
- **两阶段未整合**：目前为顺序训练，未来可探索端到端联合优化。
- **缩放行为未完全探索**：仅从6k增至12k，尚未验证更大规模下的边际效应。
- **缺乏多次实验统计**：除LLaVA-Bench外未报告误差棒，可能因计算资源限制，但单次运行结果可能受随机性影响。
- **依赖预训练模型质量**：STIC的自我提升效果受基座模型初始能力限制（作者也指出在更强的模型上提升更明显）。
- **公平性与偏差风险**：未专门讨论模型偏差问题，若训练数据存在偏差可能被放大；且模型可能用于生成误导性信息。

（完）
