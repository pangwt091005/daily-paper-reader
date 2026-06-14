---
title: "CyIN: Cyclic Informative Latent Space for Bridging Complete and Incomplete Multimodal Learning"
title_zh: CyIN：桥接完整与不完整多模态学习的循环信息潜在空间
authors: "Ronghao Lin, Qiaolin He, Sijie Mai, Ying Zeng, Aolin Xiong, Li Huang, Yap-Peng Tan, Haifeng Hu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=feuFyonHks"
tags: ["query:nutritionk"]
score: 5.0
evidence: 处理缺失模态的多模态学习框架
tldr: 该论文针对多模态学习在真实部署中模态缺失导致性能下降的问题，提出Cyclic Informative Learning (CyIN)框架，通过标记级和标签级信息瓶颈构建信息潜在空间，弥合完整与不完整模态学习之间的差距。实验表明该方法能显著提升缺失模态下的鲁棒性，为食品图像营养预测等多模态任务提供了可迁移的稳健训练策略。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-feufyonhks/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1369, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-feufyonhks/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 703, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1387, \"height\": 988, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1408, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 648, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1379, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 809, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1387, \"height\": 1954, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1349, \"height\": 2282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1462, \"height\": 735, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1113, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 816, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 685, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-feufyonhks/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 652, \"height\": 203, \"label\": \"Table\"}]"
motivation: 现有模型在模态缺失时性能骤降，需要鲁棒的多模态学习框架。
method: 提出CyIN框架，采用令牌级和标签级信息瓶颈构建循环信息潜在空间。
result: 在多个多模态基准上，缺失模态下性能显著优于基线。
conclusion: CyIN有效提升了多模态模型在动态缺失模态场景下的鲁棒性。
---

## Abstract
Multimodal machine learning, mimicking the human brain’s ability to integrate various modalities has seen rapid growth. Most previous multimodal models are trained on perfectly paired multimodal input to reach optimal performance. In real‑world deployments, however, the presence of modality is highly variable and unpredictable, causing the pre-trained models in suffering significant performance drops and fail to remain robust with dynamic missing modalities circumstances. In this paper, we present a novel Cyclic INformative Learning framework (CyIN) to bridge the gap between complete and incomplete multimodal learning. Specifically, we firstly build an informative latent space by adopting token- and label-level Information Bottleneck (IB) cyclically among various modalities. Capturing task-related features with variational approximation, the informative bottleneck latents are purified for more efficient cross-modal interaction and multimodal fusion. Moreover, to supplement the missing information caused by incomplete multimodal input, we propose cross-modal cyclic translation by reconstruct the missing modalities with the remained ones through forward and reverse propagation process. With the help of the extracted and reconstructed informative latents, CyIN succeeds in jointly optimizing complete and incomplete multimodal learning in one unified model. Extensive experiments on 4 multimodal datasets demonstrate the superior performance of our method in both complete and diverse incomplete scenarios.

---

## 论文详细总结（自动生成）

# 论文中文总结：CyIN: 循环信息潜在空间桥接完整与不完整多模态学习

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现实部署中多模态输入（如语言、音频、视觉）常因传感器故障等原因导致模态缺失，而预训练模型在缺失模态时性能显著下降。现有方法要么通过对齐（对比学习等）要么通过生成（自编码器、扩散模型等）来缓解，但存在缺失信息利用不充分、受任务无关噪声干扰、需为每种缺失组合训练单独模型、且往往牺牲完整模态性能等不足。
- **研究目标**：构建一个统一框架，同时优化完整模态学习与不完整模态学习，使模型在各类缺失场景下保持鲁棒，且不牺牲完整输入时的性能。
- **整体含义**：提出CyIN（Cyclic INformative Learning）框架，通过**信息瓶颈（IB）** 构建**循环信息潜在空间**，实现跨模态的信息压缩、交互与缺失模态的循环重建，从而在一个模型中无缝衔接完整与不完整多模态学习。

## 2. 方法论

### 核心思想
利用信息瓶颈（IB）原则，在低层（token级）和语义高层（标签级）两个层面循环地对各模态特征进行压缩与目标导向的提炼，得到纯净的任务相关瓶颈潜在表示。在此基础上，设计**跨模态循环翻译**机制，用留存模态的重建缺失模态，并通过前向-反向传播增强翻译质量。最终在统一的潜在空间中进行多模态融合与预测。

### 关键技术细节
1. **Token级信息瓶颈（Token-level IB）**：
   - 针对任意两个模态（源S与目标T），在每个token嵌入上施加IB：最小化I(S;B)，同时最大化I(B;T)。利用变分近似得到可微损失：
     \[ L_{S\to T}^{tib} \approx \frac{1}{L}\sum_i \left\{ \text{KL}(\mathcal{N}(\mu_B^{(i)},\sigma_B^{(i)2})\|\mathcal{N}(0,\mathbf{I})) + \beta \mathbb{E}_{b_S}[\|f_T - D_T(b_S)\|^2] \right\} \]
   - **循环交互**：交替选择S/T为相同模态（自模态压缩）或不同模态（跨模态对齐），最终损失为 \(L_{tib} = \mathbb{E}_{S,T}[L_{S\to S}^{tib} + \frac12(L_{S\to T}^{tib}+L_{T\to S}^{tib})]\)。

2. **标签级信息瓶颈（Label-level IB）**：
   - 以真实标签\(y_{gt}\)为目标，对每个模态的表示施加IB，通过预测器\(P_S\)输出预测\(\hat{y}_S\)。
   - 回归任务：\(q_\phi(y_{gt}|B_S)=e^{-\|y_{gt}-\hat{y}_S\|}\) → 损失含\(\|y_{gt} - P_S(B_S)\|\)项。
   - 分类任务：\(q_\phi(y_{gt}|B_S)=\prod \hat{y}_S^{y_{gt}}\) → 损失含交叉熵项。
   - 整体\(L_{lib}\)包含KL散度与预测项，迭代所有模态。

3. **跨模态循环翻译（Cross-modal Cyclic Translation）**：
   - 利用**级联残差自编码器（CRA）** 作为翻译器\(\Gamma_{S\to T}\)，从源瓶颈\(B_S\)生成目标瓶颈\(B_{rec}^{S\to T}\)。
   - **前向传播**：\(B_{rec}^{S\to T} = \Gamma_{S\to T}(B_S)\)，重建损失\(L_{S\to T}^{rec} = \|B_T - B_{rec}^{S\to T}\|^2\)。
   - **反向传播**：将重建结果翻译回源模态：\(B_{cyc}^S = \Gamma_{T\to S}(B_{rec}^{S\to T})\)，循环一致性损失\(L_{T\to S}^{cyc} = \|B_S - B_{cyc}^S\|^2\)。
   - **多留存模态泛化**：当有多个留存模态时，利用高斯分布可加性，将各翻译器输出求和（或乘积形式）得到最终缺失模态瓶颈\(\hat{B}_{miss}\)。

4. **多模态融合与训练**：
   - 采用**多模态Transformer**对各模态瓶颈进行交叉注意力融合得到\(F_M\)，再经MLP预测。
   - 总损失：\(L_{total} = L_{task} + \frac1\beta(L_{tib}+L_{lib}) + \gamma L_{tran}\)。
   - **两阶段训练**：第一阶段仅优化IB损失（\(\gamma=0\)）构建信息空间；第二阶段加入翻译损失（\(\gamma>0\)）训练重建。

## 3. 实验设计

- **数据集与任务**：
  - **回归任务**：CMU-MOSI（2,199视频片段，情感连续评分-3~+3）、CMU-MOSEI（22,856片段）。
  - **分类任务**：IEMOCAP（7,369对话回合，6类情绪）、MELD（13,391对话语句，7类情绪）。
- **Benchmark与对比方法**：共9种基线：CCA、DCCA、DCCAE、CPM-Net、CRA、MCTN、MMIN、GCNet、IMDer、LNLN。这些方法覆盖经典多视图学习、循环翻译、图网络、扩散模型等。
- **评估协议**：
  - **完整输入**（\(u\in\{l,a,v\}\)）。
  - **固定缺失**：分别缺失一个或两个模态（如\(\{l\},\{v\},\{a\},\{l,a\},\{l,v\},\{a,v\}\)）。
  - **随机缺失**：缺失率\(MR\in\{0.1,0.2,...,0.7\}\)，每个样本随机缺失1-2种模态。
  - 每个设置跑10次取均值，保证公平。
- **评价指标**：回归用Acc7、F1、MAE、Corr；分类用Acc、wF1。

## 4. 资源与算力

- 所有实验在**H800 GPU**上进行，使用**PyTorch 2.4.1**、**CUDA 12.4**。
- 文中未明确说明使用的GPU数量、总训练时长或具体算力消耗。但在计算效率对比（表5）中给出了总参数量（123.49M）、总训练时间（1.61h）、推理时间（22.41s/iteration）及FLOPs（1.594T）。相较于GCNet和IMDer，CyIN参数更少、推理更快，但训练时间略长于GCNet。

## 5. 实验数量与充分性

- 共涉及**4个数据集**（两种任务类型），覆盖**完整输入**、**6种固定缺失**、**7种随机缺失率**，每个实验10次随机种子重复，样本量丰富。
- **消融实验**（表2）：在MOSI和IEMOCAP上分别针对完整与高缺失率（MR=0.7）考察了：去掉Token级IB、去掉Label级IB、去掉循环交互、去掉循环翻译、去掉信息空间（即不施加瓶颈约束）、去掉重建潜在（直接填充零）等变体。
- **超参数敏感性实验**（表3、表4）：测试了\(\beta\)和\(\gamma\)的不同取值，以及翻译器中CRA层数在不同模态对中的比例。
- **稳定性分析**（附录表9）：报告了10次运行的标准差。
- **额外泛化实验**（附录表10-13）：扩展了不同规模语言模型、多模态推荐、人脸反欺诈、密集预测、医学分割等任务，验证框架的可迁移性。
- 实验设计**较为充分**，对比基线全面，消融覆盖了关键组件，协议细致（固定+随机)，结果客观公平。

## 6. 主要结论与发现

- 在**完整模态**下，CyIN在MOSI/MOSEI/IEMOCAP/MELD上均达到或超越SOTA（如MOSI Acc7=48.0，F1=86.3，优于LNLN等）。
- 在**固定缺失**场景下，CyIN同样取得最优或接近最优的结果，尤其在弱模态（音频、视觉）单独存在时提升显著，体现了对模态不平衡的鲁棒性。
- 在**随机缺失**场景下，即使缺失率高达70%，CyIN的性能下降幅度最小，始终领先于所有基线，证明其泛化能力强。
- **消融实验**证实：Token级+Label级IB、循环交互/翻译、信息空间约束三者缺一不可；重建潜在显著提升缺失性能。
- **定性分析**（t-SNE、案例研究）显示：翻译瓶颈与原始瓶颈分布接近，重建后的多模态表示聚类更优，预测更准确。
- 框架具有**通用性**，可扩展到不同模态数量、不同任务（推荐、分割等）。

## 7. 优点

1. **理论创新**：将信息瓶颈（IB）引入多模态缺失学习，巧妙结合token级与label级IB，实现特征提纯与任务导向。
2. **循环架构**：通过前向与反向翻译实现跨模态信息重建，利用循环一致性约束增强翻译质量，且无需为每种缺失组合训练独立模型。
3. **统一模型**：在一个框架内同时处理完整与不完整输入，不牺牲完整性能，且训练好的模型可直接应对各种缺失比例。
4. **实验全面**：在4个主流情感分析数据集、多种缺失协议、多个基线上进行验证，消融与超参数分析清晰。
5. **计算效率**：相比IMDer、GCNet等，参数量和推理时间更优，实际部署潜力大。
6. **可扩展性**：通过高斯分布可加性推广到多模态场景，实验显示在推荐、分割等其他任务上也表现良好。

## 8. 不足与局限

1. **模态等权假设**：框架默认各模态贡献相等，忽略了语言等主导模态可能需更高权重。作者提议未来自适应分配权重。
2. **翻译器有待升级**：当前使用级联残差自编码器（CRA），作者指出可替换为扩散模型或流模型以提升重建效果。
3. **未与大型语言模型集成**：仅在实验部分测试了不同预训练语言模型，但未与LLM（如LLaMA）结合；未来可探索扩展性。
4. **未对所有任务进行大规模测试**：虽然增加了额外任务验证，但主要实验集中在情感分析领域，在更广泛的多模态任务（如视频理解、机器人感知）上效果未知。
5. **资源报告不完整**：未明确说明GPU数量、总GPU小时数，仅提供相对比较，不利于复现硬件需求评估。
6. **潜在偏差风险**：用于情感分析的语料可能带有文化偏见，缺失模态重建可能引入人工痕迹，需关注公平性与真实性。

（完）
