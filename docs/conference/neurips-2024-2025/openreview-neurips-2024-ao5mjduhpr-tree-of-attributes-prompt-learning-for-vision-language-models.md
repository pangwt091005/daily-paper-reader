---
title: Tree of Attributes Prompt Learning for Vision-Language Models
title_zh: 视觉语言模型的属性树提示学习
authors: "Tong Ding, Wanhua Li, Zhongqi Miao, Hanspeter Pfister"
date: 2024-05-15
pdf: "https://openreview.net/pdf?id=AO5MjDuHpr"
tags: ["query:nutritionk"]
score: 4.0
evidence: 视觉语言模型的属性树提示学习
tldr: 现有提示学习方法仅将可学习标记与类别名拼接，未能充分利用语义上下文。TAP方法先让大语言模型生成概念-属性-描述的三层属性树，再结合视觉和文本提示学习该层次结构。实验证明，TAP在多个零样本分类基准上取得最优，尤其擅长细粒度识别。
source: NeurIPS-2024-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ao5mjduhpr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1388, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ao5mjduhpr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1408, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ao5mjduhpr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 899, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ao5mjduhpr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1420, \"height\": 293, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ao5mjduhpr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1413, \"height\": 1059, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ao5mjduhpr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ao5mjduhpr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1129, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ao5mjduhpr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 524, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ao5mjduhpr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 481, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ao5mjduhpr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 794, \"height\": 228, \"label\": \"Table\"}]"
motivation: 现有提示学习未能充分利用类别名的丰富语义上下文。
method: 利用大语言模型生成属性树，并学习层次化的视觉文本提示。
result: 在多个零样本分类任务上达到新最优，尤其提升细粒度识别。
conclusion: 属性树提示学习有效注入结构化知识，提升VLM下游适应能力。
---

## Abstract
Prompt learning has proven effective in adapting vision language models for downstream tasks. However, existing methods usually append learnable prompt tokens solely with the category names to obtain textual features, which fails to fully leverage the rich context indicated in the textual category name. To address this issue, we propose the Tree of Attributes Prompt learning (TAP), which first instructs LLMs to generate a tree of attributes with a ``concept - attribute - description'' structure for each associated category name, and then learn the hierarchy with vision and text prompt tokens. Unlike existing methods that merely augment category names with a set of unstructured descriptions, our approach essentially distills structured knowledge graphs associated with class names from LLMs. Furthermore, our approach introduces text and vision prompts designed to explicitly learn the corresponding visual attributes, effectively serving as domain experts. Additionally, the general and diverse descriptions generated based on the class names may be wrong or absent in the specific given images. To address this misalignment, we further introduce a vision-conditional pooling module to extract instance-specific text features. Extensive experimental results demonstrate that our approach outperforms state-of-the-art methods on the zero-shot base-to-novel generalization as well as few-shot classification across 11 diverse datasets.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：视觉语言模型（VLM，如CLIP）通过提示学习（prompt learning）能有效适应下游任务。现有方法通常仅将可学习的提示标记与类别名称拼接，以获得文本特征，但这种方式未能充分利用类别名称背后的丰富语义上下文。
- **问题**：传统的提示学习（如CoOp）使用“a photo of a {class}”之类的简单模板，缺乏深度；利用大语言模型（LLM）生成描述的方法虽能提供更多细节，但描述通常是无结构、杂乱堆叠的，且可能包含与具体图像不相关甚至错误的描述，导致图文对齐不准。
- **意义**：如何结构化地组织LLM生成的描述，并自适应地为每张图像选择最相关的描述，以提升VLM在下游任务中的表现。

## 2. 提出的方法论
- **核心思想**：提出“属性树提示学习”（Tree of Attributes Prompt Learning，TAP）。核心是构建一个层次化的“概念-属性-描述”知识树（即从LLM中蒸馏出结构化知识图谱），并用视觉和文本提示学习该层次结构。
- **关键技术细节**：
  - **属性树生成**：三步法：(1) 属性生成：让LLM为数据集生成一组视觉属性（如颜色、形状、纹理等）；(2) 示例生成：随机选一个类，按属性生成描述，人类审核；(3) 为所有类生成描述。形成“根节点（类名）→属性节点→叶子节点（具体描述）”的树结构。
  - **视觉专家标记**：在视觉编码器输入端插入一组可学习的“视觉专家标记”（vision expert tokens），每个标记对应一个属性（如颜色、形状），模仿领域专家，专注于学习该属性的视觉特征。与传统的仅靠CLS token捕获全局信息不同，这些专家标记通过深层提示（deep prompting）与零初始化残差连接，在Transformer各层中提供显式的属性引导。
  - **文本上下文标记**：在文本编码器中引入可学习的上下文标记（text context tokens），共享所有描述。
  - **视觉条件池化（VCP）**：为每个属性构建一个注意力池化模块，以图像特征（使用对应的视觉专家标记作为查询）为条件，对属性描述集进行加权求和，动态选出最匹配当前图像的描述。公式：Query = W_q·p_v^a, Key = W_k·Emb(D_a^c)，Attention Score = softmax(Query·Key^T)，v_a^c = Attention Score·Emb(D_a^c)。
  - **训练目标**：对比损失（每个专家标记与其对应的属性文本特征对齐）+ 正则化损失（保持原始CLIP知识）。
  - **推理融合**：CLS token的全局预测与各属性专家预测的加权组合（超参数α控制权重）。
- **算法流程**：训练时，冻结CLIP视觉和文本编码器的主干，仅优化视觉专家标记、文本上下文标记、VCP层参数以及少量可学习层。迭代训练（视觉5个epoch，文本1个epoch，总共50或100个epoch）。

## 3. 实验设计
- **数据集**：11个图像识别数据集，涵盖通用对象识别（ImageNet, Caltech101）、细粒度分类（OxfordPets, StanfordCars, Flowers102, Food101, FGVCAircraft）、场景识别（SUN397）、动作识别（UCF101）、纹理分类（DTD）、卫星图像分析（EuroSAT）。
- **Benchmark设置**：
  - **基类到新类泛化（Base-to-Novel Generalization）**：将每个数据集类别均匀分为基类和新类，在基类上训练，在新类上零样本测试。主要评价指标：基类准确率、新类准确率、调和平均（HM）。
  - **少样本分类（Few-shot Classification）**：每个类别16个样本，训练后测试。
- **对比方法**：CLIP（零样本基线）、CoOp、Co-CoOp、ProGrad、RPO、LoGoPrompt、PromptSRC（SOTA）等。
- **结果**：
  - 基类→新类泛化：TAP平均调和平均81.04%，比PromptSRC（79.97%）提升1.07%，比CLIP（71.70%）提升9.34%。尤其在新类准确率上提升明显（77.63% vs PromptSRC 76.10%）。
  - 少样本分类：平均准确率83.37%，超过PromptSRC（82.87%）和其他方法。
  - 在细粒度任务（DTD、EuroSAT、UCF101）上提升显著，新类准确率分别提升5.03%、8.27%、3.63%。

## 4. 资源与算力
- **文中说明**：使用PyTorch，单张NVIDIA A100-80GB GPU实现所有实验。训练时：基类→新类实验视觉编码器训练50个epoch，文本编码器10个epoch；少样本实验则分别为100和20个epoch。具体总训练时长未明确给出，但提到每次实验运行3次取平均。
- **未说明**：未提供精确的GPU小时数或总计算量，但基于单卡A100和中等epoch数，算力需求在可接受范围内。

## 5. 实验数量与充分性
- **实验数量**：涵盖了11个数据集上的两大设置（基类→新类泛化和少样本分类），以及详细的消融实验（属性树结构 vs 无结构、视觉专家标记 vs CLS token、属性数量影响、VCP池化设计对比）。
- **充分性**：
  - 实验设计较为全面，覆盖多种识别场景，且与多个最新方法对比，结果具有竞争力。
  - 消融实验验证了各关键组件的贡献，例如结构化属性树优于无组织描述，VCP优于平均池化和注意力最大池化。
  - 运行3次取平均，增加可信度。
  - **客观性**：方法在11个数据集上均表现出一致优势，尤其在细粒度任务上提升明显，说明方法泛化性强。但未报告误差棒或统计显著性检验，略微降低说服力。

## 6. 主要结论与发现
- **结论**：TAP通过结构化属性树、视觉专家标记和视觉条件池化，显著提升了VLM在零样本泛化和少样本分类上的性能，达到新SOTA。该方法有效解决了LLM生成描述的无结构、不相关等问题，并实现了属性级别的精细对齐。
- **发现**：属性树结构比无组织描述带来2%以上的提升；视觉专家标记比单一CLS token更有助于细粒度理解；VCP能根据图像内容动态选择最匹配的描述，提升对齐质量。

## 7. 优点
- **结构创新**：首次将LLM生成的描述组织为“概念-属性-描述”层次树，本质是从LLM中蒸馏结构化知识图谱，而非简单堆砌。
- **领域专家设计**：为每个属性设置独立的视觉可学习标记，并将它们作为一种“领域专家”，允许模型从不同角度聚焦图像区域，提高了可解释性（GradCAM可视化证实）。
- **自适应性**：VCP模块根据图像内容动态池化描述，解决了描述冗余和干扰问题，且注意力权重可视化直观展示了其有效性。
- **性能优越**：在11个数据集上均达到或超越SOTA，尤其在细粒度任务上提升显著，证明方法鲁棒且通用。
- **参数高效**：仅微调少量可学习标记和VCP层，冻结CLIP主干，训练快速。

## 8. 不足与局限
- **对LLM的依赖**：描述生成质量直接影响结果。在极端细粒度数据集（如FGVCAircraft）上，LLM可能为相似类别生成相同描述，导致新类预测性能受限（文中承认该局限性）。
- **实验细节缺失**：未报告误差棒或置信区间，统计显著性不明；算力消耗未详细量化；超参数α（0.4）固定，未进行细致的跨数据集调优分析。
- **部署与计算成本**：虽然训练参数少，但VCP和专家标记的引入增加了推理阶段的多路计算（每个属性都需要计算注意力），可能影响速度。
- **潜在偏差风险**：LLM生成的属性描述可能携带训练数据中的偏见（如性别、种族相关视觉特征），论文虽在附录中提及社会影响，但未在实验中系统评估公平性。
- **仅测试了ViT-B/16骨干**：未验证其他CLIP架构（如ResNet、ViT-L）上的泛化能力，可能引入了模型依赖性。

（完）
