---
title: Amplifying Prominent Representations in Multimodal Learning  via Variational Dirichlet Process
title_zh: 通过变分狄利克雷过程放大多模态学习中的显著表示
authors: "Tsai Hor Chan, Feng Wu, Yihang Chen, Guosheng Yin, Lequan Yu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=dC5TWysDsZ"
tags: ["query:nutritionk"]
score: 5.0
evidence: 基于狄利克雷过程的多模态融合
tldr: 该论文针对多模态融合中过分强调跨模态对齐而抑制各模态内部特征表达的问题，引入变分狄利克雷过程，利用其“富者愈富”特性放大每个模态中的显著表示，同时学习跨模态交互。在医疗和金融等真实场景数据集上，该方法在保留模态独有特征的同时提升了融合效果，可应用于食品营养预测中的图像与文本特征协同分析。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 695, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 706, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 698, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dc5twysdsz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 707, \"height\": 411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 706, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 940, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 868, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1443, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1447, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 796, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1012, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1008, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dc5twysdsz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1294, \"height\": 372, \"label\": \"Table\"}]"
motivation: 现有融合方法过度对齐模态分布，导致内部有意义表示受损。
method: 利用变分狄利克雷过程混合模型，动态分配权重以放大各模态显著特征。
result: 在多模态分类任务上优于现有融合方法，尤其模态差异大时。
conclusion: 狄利克雷过程有效平衡了模态内表达与跨模态交互。
---

## Abstract
Developing effective multimodal fusion approaches has become increasingly essential in many real-world scenarios, such as health care and finance. 
The key challenge is how to preserve the feature expressiveness in each modality while learning cross-modal interactions.
Previous approaches primarily focus on the cross-modal alignment,
while over-emphasis on the alignment of marginal distributions of modalities may impose excess regularization and obstruct meaningful representations within each modality.
The Dirichlet process (DP) mixture model is a powerful Bayesian non-parametric method that can amplify the most prominent features by its richer-gets-richer property, which allocates increasing weights to them.
Inspired by this unique characteristic of DP, we propose a new DP-driven multimodal learning framework that automatically achieves an optimal balance between prominent intra-modal representation learning and cross-modal alignment. 
Specifically, we assume that each modality follows a mixture of multivariate Gaussian distributions and further adopt DP to calculate the mixture weights for all the components. This paradigm allows DP to dynamically allocate the contributions of features and select the most prominent ones, leveraging its richer-gets-richer property, thus facilitating multimodal feature fusion.
Extensive experiments on several multimodal datasets demonstrate the superior performance of our model over other competitors.
Ablation analysis further validates the effectiveness of DP in aligning modality distributions and its robustness to changes in key hyperparameters.
Code is anonymously available at https://github.com/HKU-MedAI/DPMM.git

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态融合中，现有方法（如对比学习、对抗对齐）过度强调跨模态分布的强制对齐，导致每个模态内部有意义的特征表示被压缩或丢失，从而削弱了下游任务性能，尤其在模态高度异构（如医疗图像与结构化表格数据）时更为严重。
- **研究动机**：希望既能有效对齐不同模态分布，又能保留甚至放大各模态内的显著特征。
- **整体含义**：引入贝叶斯非参数方法中的**狄利克雷过程（Dirichlet Process, DP）**，利用其“富者愈富”（richer-gets-richer）特性，自动为每个模态中最突出的特征分配更大权重，从而在融合过程中保持特征表达力。

### 2. 论文提出的方法论

- **核心思想**：将多模态联合特征分布建模为**DP混合模型**（Dirichlet Process Mixture Model）。每个模态的特征服从一个多元高斯混合分布，其中混合权重通过DP的stick-breaking过程动态生成，使得DP能够自动选择并放大各模态中最显著的成分。
- **关键技术细节**：
  - **Stick-breaking过程**：按模态→成分的顺序递归拆分，生成权重 \(\pi_{mk}\)。
  - **高斯混合边际分布**：假设第 \(m\) 个模态的特征分布为 \(f_m(z) = \sum_{k=1}^K \pi_{mk} \mathcal{N}(z|\mu_{mk}, \Sigma_{mk})\)，其中 \(\Sigma_{mk}\) 为对角协方差矩阵（参数化技巧）。
  - **变分推理**：采用随机变分推断（SVI）优化ELBO，可大规模训练。ELBO包含KL散度项（先验与后验之间）和任务损失。
  - **缺失模态处理**：假设缺失机制为随机缺失（MAR），利用学习到的边际分布 \(F_m\) 通过梯度保持采样生成缺失模态的表示，从而保留主要特征。
- **算法流程**（文字说明）：
  1. 初始化各高斯分量的均值 \(\mu_{mk}=0\)、协方差 \(\Sigma_{mk}=I\)。
  2. 对每个样本，经编码器得到嵌入 \(z_m\)。
  3. 通过stick-breaking过程计算当前权重 \(\pi_{mk}\)。
  4. 计算加权似然及任务损失（如交叉熵）。
  5. 计算ELBO，反向传播更新编码器参数及 \(\mu, \Sigma\)。
  6. 通过变分更新公式（式(4)）更新后验Beta参数。

### 3. 实验设计

- **数据集与场景**：
  - **医疗数据集**：MIMIC-III（EHR + 临床笔记）、MIMIC-IV（EHR + 胸部X光片 + 放射报告），任务为住院死亡率（IHM）和30天再入院（READM）预测。
  - **通用多模态数据集**：CMU-MOSI（视频、音频、文本）用于情感分析；POM用于电影特质预测。
  - 实验场景包括**完全匹配**（所有模态存在）、**部分匹配**（部分样本缺失某些模态）以及**三模态**场景。
- **Benchmark 对比方法**：
  - 医疗基准：MMTM、DAFT、Unified、MedFuse、DrFuse。
  - 通用基准：LMF（低秩张量融合）、TFN（张量融合网络）。
  - 额外对比：CLIP、ALIGN、CoMM（对比学习模型）、PSA、LSMT（缺失插补方法）。
- **评价指标**：AUROC、AUPR、F1（医疗任务）；MAE、Accuracy、Corr（情感分析任务）。

### 4. 资源与算力

- **硬件**：单块 NVIDIA RTX-3090 GPU。
- **训练设置**：batch size 32（MIMIC-IV&CXR）或16（MIMIC-III&NOTE）；训练100个epoch，使用早停（验证AUROC连续15轮不提升则停止）。
- **时间成本**：附录中给出每epoch时间（完全匹配约26.57s，部分匹配约70.80s），未明确总训练时长。未使用多GPU或分布式训练。

### 5. 实验数量与充分性

- **实验数量**：
  - 主要结果：两个医疗数据集×两个任务×两个场景（完全/部分匹配）→至少8组主实验。
  - 通用数据集：CMU-MOSI和POM各一组实验。
  - 消融实验：
    - 组件消融（有无对齐、有无梯度保持采样、有无融合模块）→8组。
    - 对齐损失对比（余弦、KL、DP）→2组。
    - 超参数η和K的网格搜索（η={0.1,0.5,1,2,5}，K={2,3,4,5}）→25组。
    - 不同缺失率（10%、40%、70%）→多组。
    - DP权重 vs 可学习权重→2组。
    - 与更多插补方法（PSA、LSMT）对比→2组。
    - 与对比学习模型（CLIP、ALIGN、CoMM）对比→1组。
    - 分离放大与对齐效果→2组。
  - 总计约50+组实验。
- **充分性**：实验覆盖多种模态组合、多个缺失场景、多组消融，且报告了95%置信区间（bootstrap），对比方法设置公平（相同编码器、超参数调优）。实验设计较为充分、客观。

### 6. 论文的主要结论与发现

- **性能优势**：DPMM在所有数据集和任务上均优于现有SOTA方法，尤其在全匹配和部分匹配场景下AUROC、AUPR提升显著（例如MIMIC-IV IHM任务AUROC提升1-4%，AUPR提升8%）。
- **特征放大与对齐**：可视化表明DP的前几个高斯分量具有更高对数密度，验证了“富者愈富”特性确实选择了显著特征。
- **鲁棒性**：对超参数η和K变化不敏感（图6），且在不同缺失率下性能下降幅度小于对比方法。
- **缺失模态处理有效**：利用DP边际分布生成的缺失表示能保留主要特征，显著优于零填充或全局表示方法。

### 7. 优点

- **方法创新**：首次将狄利克雷过程引入多模态融合，巧妙利用其特性平衡特征保留与对齐，思想新颖。
- **理论保证**：引用Ishwaran & Zarepour定理说明截断后收敛性，保证有限混合仍具表达力。
- **实验严谨**：覆盖医疗和通用场景，提供置信区间，消融全面，超参数分析细致。
- **实际价值**：能自然处理缺失模态，适用于临床等常见缺失场景，代码已公开。
- **可扩展性**：采用变分推理而非MCMC，可扩展至大规模数据。

### 8. 不足与局限

- **协方差假设**：当前假设对角协方差，未探索全协方差或Wishart先验，可能限制对特征相关性的建模能力。
- **DP结构简单**：仅使用单层DP，未探索层次DP或多层变体，作者在“Limitations”中也承认这一点。
- **计算成本**：虽在单GPU可运行，但每epoch时间约为同类方法的1.2-1.5倍，超大规模数据下可能成为瓶颈（附录表D.6）。
- **缺失机制假设**：仅采用MAR假设，未考虑非随机缺失（MNAR）场景。
- **理论深度**：除截断收敛性引理外，缺乏对DP权重动态分配的理论分析（如收敛速率、泛化界）。
- **应用范围**：主要验证在医疗和少量情感分析任务，未在更多领域（如自动驾驶、视频理解）测试。
- **消融独立性**：部分消融（如“无对齐”）等价于直接去掉DP组件，可能与基线方法不对等，但整体仍不失公平。

（完）
