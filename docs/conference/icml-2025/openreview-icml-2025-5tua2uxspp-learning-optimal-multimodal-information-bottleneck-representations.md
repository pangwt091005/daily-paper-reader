---
title: Learning Optimal Multimodal Information Bottleneck Representations
title_zh: 学习最优多模态信息瓶颈表征
authors: "Qilong Wu, Yiyang Shao, Jun Wang, Xiaobo Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=5TUa2UXSpp"
tags: ["query:nutritionk"]
score: 6.0
evidence: 最优多模态信息瓶颈通用方法，可应用于食品营养成分分析
tldr: 该论文提出最优多模态信息瓶颈（OMIB）框架，通过优化目标保证实现最优多模态信息瓶颈，解决现有方法权重设置随意和忽视跨模态信息不平衡的问题。该通用多模态学习方法可直接应用于食品图像与文本的营养成分预测，提升多模态融合效率和预测准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 789, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 791, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1579, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 825, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 886, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5tua2uxspp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 892, \"height\": 548, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 894, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1174, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 470, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 857, \"height\": 116, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5tua2uxspp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 945, \"height\": 963, \"label\": \"Table\"}]"
motivation: 现有基于多模态信息瓶颈的方法因权重设置随意和忽视跨模态信息不平衡而无法达到最优。
method: 提出OMIB框架，通过优化目标保证实现最优多模态信息瓶颈。
result: 在多个多模态任务上评估，OMIB优于现有MIB方法。
conclusion: OMIB为多模态食品营养预测提供了强有力的通用融合技术。
---

## Abstract
Leveraging high-quality joint representations from multimodal data can greatly enhance model performance in various machine-learning based applications. Recent multimodal learning methods, based on the multimodal information bottleneck (MIB) principle, aim to generate optimal MIB with maximal task-relevant information and minimal superfluous information via regularization. However, these methods often set regularization weights in an *ad hoc* manner and overlook imbalanced task-relevant information across modalities, limiting their ability to achieve optimal MIB. To address this gap, we propose a novel multimodal learning framework, Optimal Multimodal Information Bottleneck (OMIB), whose optimization objective guarantees the achievability of optimal MIB by setting the regularization weight within a theoretically derived bound. OMIB further addresses imbalanced task-relevant information by dynamically adjusting regularization weights per modality, ensuring the inclusion of all task-relevant information. Moreover, we establish a solid information-theoretical foundation for OMIB's optimization and implement it under the variational approximation framework for computational efficiency. Finally, we empirically validate the OMIB’s theoretical properties on synthetic data and demonstrate its superiority over the state-of-the-art benchmark methods in various downstream tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基于多模态信息瓶颈（Multimodal Information Bottleneck, MIB）的方法存在三个主要局限：
  1. 正则化权重（β）设置随意，无法保证达到最优MIB；
  2. 忽视跨模态任务相关信息的不平衡，可能导致重要模态的信息被过度压缩；
  3. 缺乏全面的信息论理论支撑，未能明确区分一致、互补、冗余等信息要素。
- **整体含义**：提出最优多模态信息瓶颈（Optimal Multimodal Information Bottleneck, OMIB）框架，通过理论推导的边界设定正则化权重，并动态调整各模态的正则化强度，从而保证学习到的MIB表征包含所有任务相关信息且排除冗余信息，提升下游任务性能。该方法可广泛应用于多模态分类、回归、异常检测等场景。

## 2. 方法论

- **核心思想**：在MIB原则基础上，引入动态权重r和理论上界Mu，保证目标函数优化过程中能够达到最优MIB（即表征仅包含任务相关信息，不含冗余信息）。
- **关键技术细节**：
  - **Warm-up阶段**：对每个模态训练任务相关性分支（TRB），提取充分表征zi（满足I(zi;y)=I(vi;y)），通过加入随机高斯噪声强制编码器学习高信噪比表征。
  - **Main阶段**：包括最优多模态融合块（OMF）：
    1. 对zi输入VAE生成ζi（重参数化）；
    2. 使用交叉注意力网络（CAN）融合多个ζi得到ξ；
    3. 预测头dDec输出ˆy。
  - **目标函数**（以两模态为例）：
    \[
    \min_\xi \ell(\xi) = \min_\xi -I(\xi;y) + \beta (I(\xi;z_1) + r I(\xi;z_2))
    \]
    其中β为冗余正则权重，r为动态调整的相对权重（计算公式：r = 1 - tanh(ln(平均KL比值))，反映模态间剩余任务相关信息比值）。
  - **理论上界Mu**：
    \[
    M_u = \frac{1}{3(H(v_1)+H(v_2)-I(v_1;v_2))}
    \]
    使用MINE（Mutual Information Neural Estimator）从训练数据预估H和I。实际使用[M_l, M_u]区间（M_l = 1/(3(H(v1)+H(v2)))）加速训练。
  - **变分上界**：推导出可计算的L_OMF损失，包含交叉熵（或MSE/SVDD）项和KL散度项。
- **算法流程**：详见附录L（Algorithm 1: Warm-up training; Algorithm 2: Main training）。

## 3. 实验设计

- **数据集/场景**：
  - **合成数据（SIM-I/II/III）**：高斯分布生成，控制任务相关信息在模态间的分布（不平衡/平衡），用于验证β上界和最优MIB理论。
  - **情感识别**：CREMA-D（6类情感，视频+音频）。
  - **多模态情感分析**：CMU-MOSI（图像+音频+文本，回归任务）。
  - **异常组织检测**：8个健康乳腺组织数据集（10x-hNB-{A-H}）训练，4个乳腺癌数据集（10x-hBC-{A-D}）测试（基因表达+组织学图像）。
- **Benchmark方法**：
  - 非MIB-based：Concat、BiGated、MISA。
  - MIB-based：deep IB、MMIB-Cui、MMIB-Zhang、DMIB、E-MIB、L-MIB、C-MIB。
- **评估指标**：准确率、F1、MAE、Corr、AUC等。

## 4. 资源与算力

- 文中仅说明所有实验使用PyTorch实现，**未明确提及GPU型号、数量、训练时长**等具体算力资源信息。

## 5. 实验数量与充分性

- **实验数量**：
  - 合成数据：3种分布（SIM-I/II/III），验证β边界（图3）和最优MIB对比（表2）。
  - 真实任务：情感识别（1个数据集）、多模态情感分析（1个数据集）、异常检测（4个测试集）。
  - 消融实验：去掉warm-up、去掉交叉注意力、去掉整个OMF、去掉动态r（表6）。
  - 复杂度分析：不同数据规模下的运行时（图4）。
- **充分性与公平性**：
  - 对比方法全面（8种主流MIB方法+3种非MIB方法）。
  - 在多个任务上均取得最优或接近最优，验证通用性。
  - 消融实验合理，证明各组件必要性。
  - 合成数据实验直接验证理论（β上界，最优MIB优于其他信息组合）。
  - 未报告标准差或多次重复结果（表2-6均为一次性结果？），但趋势明显。

## 6. 主要结论与发现

1. **理论保证**：当β ∈ (0, M_u]时，优化OMIB目标函数可达到最优MIB（F(ξ) = {a0, a1, a2}），且动态r解决信息不平衡。
2. **合成数据验证**：β接近或低于Mu时准确率最高（图3）；OMIB生成的MIB几乎达到真实最优MIB的性能（表2）。
3. **真实任务优势**：
   - CREMA-D：准确率63.6%，超过最佳MIB方法（E-MIB 61.4%）2.2%。
   - CMU-MOSI：Acc2 86.9%，F1 87.1%，MAE 0.709，优于所有基线。
   - 异常检测：平均AUC 0.754，F1 0.737，比最佳基线分别高11.4%和3.8%。
4. **消融实验**：每个组件（warm-up、交叉注意力、OMF、动态r）均显著贡献性能。

## 7. 优点

- **理论严谨**：首次证明最优MIB在特定条件下可实现，给出显式上界和动态调整公式，连接五个信息论要素（充分性、一致性、冗余性、互补性、特异性）。
- **方法实用**：动态权重自动适应模态信息不平衡，无需手动调参；变分近似使损失可计算，训练高效。
- **实验全面**：覆盖分类、回归、异常检测多种任务，验证通用性；消融实验清晰显示组件贡献。
- **性能突出**：在三个真实场景均显著超越现有SOTA，特别是在异常检测上提升明显。

## 8. 不足与局限

- **计算资源未报告**：未提供GPU型号、训练时间、内存消耗等，难以评估实际部署成本。
- **多模态扩展有限**：理论推导以两模态为主，三模态扩展仅在附录给出，未在实验中充分验证（CMU-MOSI虽有三模态但未单独分析多模态动态权重）。
- **鲁棒性未讨论**：未实验验证对噪声模态、缺失模态或极端不平衡场景的鲁棒性。
- **异常检测方法单一**：仅使用SVDD，可考虑对比其他异常检测框架（如自编码器、GAN）。
- **可重复性细节不足**：超参数搜索过程、训练次数/种子未说明，可能影响结果稳定性。

（完）
