---
title: "Seeing the Image: Prioritizing Visual Correlation by Contrastive Alignment"
title_zh: 看见图像：通过对比对齐优先考虑视觉相关性
authors: "Xin Xiao, Bohong Wu, Jiacong Wang, Chunyuan Li, zhou Xun, Haoyuan Guo"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=NsxthTVpqA"
tags: ["query:nutritionk"]
score: 7.0
evidence: 优先训练视觉相关文本标记的对比对齐方法
tldr: 现有视觉语言模型在自回归训练中平等对待每个文本标记，导致与图像弱相关甚至矛盾的标记过度主导。CAL通过对比不同图像输入时的预测差异来衡量每个标记的视觉相关性，并据此重新加权训练。在多个基准上，CAL不仅提升对齐质量，还减少了幻觉，显著改善了图文匹配任务。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1393, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1385, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1403, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1397, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 399, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 271, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 395, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 195, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 325, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 345, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1390, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-nsxthtvpqa/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1443, \"height\": 565, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 808, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 684, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 694, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 803, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 824, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1389, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1391, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1372, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1379, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-nsxthtvpqa/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 844, \"height\": 155, \"label\": \"Table\"}]"
motivation: VLM中文本标记与图像相关性不均，平等训练导致次优对齐。
method: 通过对比图像输入的预测差异量化每个文本标记的视觉相关性，并重新加权训练。
result: 在图文对齐和生成任务上超越基线，减少幻觉并提升相关性。
conclusion: CAL为VLM提供了更精准的跨模态训练信号，适用于图像描述等应用。
---

## Abstract
Existing image-text modality alignment in Vision Language Models (VLMs) treats each text token equally in an autoregressive manner. Despite being simple and effective, this method results in sub-optimal cross-modal alignment by over-emphasizing the text tokens that are less correlated with or even contradictory with the input images. In this paper, we advocate for distinct contributions for each text token based on its visual correlation. Specifically, we present by contrasting image inputs, the difference in prediction logits on each text token provides strong guidance of visual correlation. We therefore introduce Contrastive Alignment (CAL), a simple yet effective re-weighting strategy that prioritizes training visually correlated tokens. Our experimental results demonstrate that CAL consistently improves different types of VLMs across different resolutions and model sizes on various benchmark datasets. Importantly, our method incurs minimal additional computational overhead, rendering it highly efficient compared to alternative data scaling strategies.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：当前视觉语言模型（VLM）在图像-文本模态对齐时，采用自回归的最大似然估计（MLE）损失，平等对待每个文本 token。然而，训练数据中的大量文本 token 与输入图像弱相关甚至矛盾（如模型生成数据中的幻觉内容），平等加权会导致模型过度拟合这些无关噪声，削弱跨模态对齐质量。
- **背景**：现有 VLM 优化多聚焦于数据缩放、分辨率提升或视觉编码器替换，但对齐策略本身缺乏精细设计。作者通过人类评估发现，ShareGPT4V 和 LLaVA-Instruct 数据集中约半数样本存在与图像矛盾的文本 token。
- **整体含义**：论文提出通过对比有无图像输入时的预测 logits 差异来量化每个 token 的视觉相关性，并据此重新加权训练，从而优先对齐视觉相关 token，提升模型整体性能。

## 2. 方法论

- **核心思想**：利用对比解码的思想——对于每个文本 token，计算有图像输入时的预测 logits \( \tilde{o}_{i,j}[t_j] \) 与无图像输入时的 logits \( o_{i,j}[t_j] \) 之差 \( \Delta o_{i,j}[t_j] \)。该差值能自然区分视觉相关、视觉无关和视觉矛盾的 token，差值越大表示视觉相关性越强。
- **关键技术细节**：
  1. **对比 logits 计算**：对每个训练样本，分别前向传播一次（带图像和不带图像，后者通过掩码实现），得到两个 logits 分布。
  2. **权重生成**：计算每个 token 的 \( \Delta o \)，然后进行 **clamping**（限制在 \([α, β]\)，实验设 α=1, β=5）和 **平均池化**（窗口大小 W=3）以平滑权重。
  3. **损失重加权**：最终损失为加权 MLE：
     \[
     L_{i,t_j}^{CAL} = -\frac{1}{\sum_{k=1}^l \tilde{w}_{i,t_k}} \cdot \tilde{w}_{i,t_j} \cdot \log \text{softmax}(\tilde{o}_{i,j}[t_j])
     \]
     其中权重 \( \tilde{w} \) 来自后处理的 \( \Delta o \)。
- **算法流程**（伪代码见论文 Algorithm 1）：
  - 对每个样本计算 \( o_{i,j} \) 和 \( \tilde{o}_{i,j} \)
  - 计算 \( \Delta o_{i,j}[t_j] \)
  - 执行 clamp 和 pooling 得到权重
  - 计算加权损失

## 3. 实验设计

- **数据集**：
  - **训练**：LLaVA 665k、VQA Doc、VQA Chart、ShareGPT4V、ALLaVA、LAION-GPT-4V、LIMA、OpenAssistant2、DVQA、AI2D 等（不同模型组合略有差异）。
  - **评测基准**：
    - **VQA**：VQA Text（无OCR token）、VQA Doc、VQA Chart、OCR-Bench、MMStar、MMT-Bench、SQA I、MME、POPE、SEED-I、VQA Text*（有OCR token）。
    - **图像描述**：COCO Caption（CIDEr）、TextCaps（CIDEr）。
    - **视觉定位**：RefCOCOg（val/test，IoU）。
- **对比方法**：基线模型（未加 CAL）包括 LLaVA-1.5（7B/13B）、LLaVA-NeXT（7B/13B）、MiniGemini（MGM，Gemma-2B/Vicuna-7B/13B）、MGM-HD（高分辨率版本）。所有对比均在相同训练设置下进行，确保公平。
- **实验场景**：覆盖低分辨率和高分辨率设置，多种 LLM 尺寸（2B~13B），多种视觉编码器（CLIP ViT-L、ConvNeXt-L）。

## 4. 资源与算力

- **GPU 配置**：
  - 大部分实验：16 块 NVIDIA A100（80GB）
  - LLaVA-1.5/Gemma-2B：8 块 A100
  - MGM-HD-13B：32 块 A100
- **训练时间**（以 instruction-tuning 阶段为例，16 A100）：
  - LLaVA-NeXT-7B：基线 15.6h，CAL 19.1h（增加约 22%）
  - LLaVA-NeXT-13B：基线 27.4h，CAL 33.7h（增加约 23%）
- **推理开销**：无需额外计算，与基线相同。

## 5. 实验数量与充分性

- **实验组数**：
  - **主实验**（Table 1 & Table 2）：涵盖 7 个 VQA 基准、4 个 caption/grounding 基准，在低/高分辨率下共 10 种模型配置，每个配置均有 6~7 个 benchmark 结果，共约 70+ 次性能对比。
  - **消融实验**：
    - 训练阶段（PT/IT）消融（Table 3）
    - 噪声鲁棒性实验（Figure 3）：污染数据 10%~30% 标签交换，对比基线
    - 超参数 α, β 消融（Table 4）
    - 不同对比条件（mask、Gaussian blur）消融（Table 8 & 9）
    - 平均池化效果（Table 10）
    - 预训练模型选择（Table 11）
    - 计算效率（Table 12）
  - **定性分析**：注意力图可视化（Figure 5）、图像-文本特征对齐可视化（Figure 6）。
- **充分性评价**：实验设计较为充分，覆盖了主要 VLM 框架、不同分辨率、不同尺寸，并在多个 benchmark 上验证一致性。消融实验较为全面，但缺少对统计显著性（误差棒）的报告，且部分消融（如不同 masking 比例）仅在一个模型上测试。

## 6. 主要结论与发现

1. **CAL 一致提升 VLM 性能**：在几乎所有 benchmark 上，CAL 优于或持平基线，尤其在 OCR 相关的 VQA Doc（+1.7 ANLS）、VQA Chart（+3.4 relaxed accuracy）、TextCaps（+6.2 CIDEr）等任务上提升显著。
2. **对噪声数据鲁棒**：当训练数据被人工污染（标签交换）时，CAL 的性能下降远小于基线，表明其能有效抑制矛盾 token 的影响。
3. **训练阶段影响**：主要收益来自 instruction-tuning 阶段，pre-training 阶段加入可带来额外微小提升。
4. **低成本高效率**：仅增加约 20% 训练时间，不增加推理成本。
5. **改善细粒度对齐**：定性分析显示 CAL 增强了模型对 OCR 字符的辨别能力和细节捕获能力（如区分“world”与“would”、“construction”与“consciousness”）。

## 7. 优点

- **创新性**：首次提出利用对比输入图像的 logits 差异来自动区分视觉相关 token，并用于训练重加权。
- **简洁高效**：仅需一次无梯度的额外前向传播，无需修改模型架构或增加数据。
- **广泛适用**：在多个主流 VLM（LLaVA、MGM）上均有效，涵盖不同视觉编码器、分辨率、模型大小。
- **鲁棒性**：对训练数据中的噪声（幻觉、标签错误）有天然抑制作用。
- **实验充分**：覆盖多种任务类型（VQA、caption、grounding），消融实验全面，验证了方法关键组件的作用。

## 8. 不足与局限

- **缺乏严格的 token 分类定量标准**：论文未给出明确阈值来区分视觉相关、无关、矛盾三种 token，权重设置依赖经验。
- **超参数选择依赖经验**：clamping 的上下界（α=1, β=5）和池化窗口大小（W=3）基于 logits 分布经验设定，未探索自适应方案。
- **未报告统计误差**：所有结果均为单次运行，缺少标准误或置信区间，无法评估稳定性。
- **计算开销**：虽只增加约 20%，但在大规模训练中仍属可观；且当前实现中图像 token 仍被前向两次（可通过去除图像 token 优化）。
- **应用限制**：主要针对两阶段训练范式，对端到端训练或 RLHF 方法的适用性未探讨。未考虑安全、公平等社会影响。
- **实验覆盖**：侧重 OCR、caption 等任务，对多模态推理（如 ScienceQA 数学推理）提升较小，部分 benchmark（MME、POPE）性能持平，说明方法更适用于视觉紧密相关的任务。

（完）
