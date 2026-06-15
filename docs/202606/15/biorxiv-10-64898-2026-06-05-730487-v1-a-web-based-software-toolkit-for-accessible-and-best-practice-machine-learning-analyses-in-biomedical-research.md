---
title: A Web-based software toolkit for accessible and best-practice machine learning analyses in biomedical research
title_zh: 面向生物医学研究的可访问与最佳实践机器学习分析的基于网络的软件工具包
authors: "Morais Lyra Junior, P. C., Qiu, J., Van Dang, K., Pybus, A., Narvaez-Bandera, I., Singh, M. A., Gu, Q., Sargent, L., Creason, A. L., Goecks, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730487v1.full.pdf"
tags: ["query:nutritionk"]
score: 6.0
evidence: 面向图像和多模态生物医学数据的网络ML工具包
tldr: 生物医学研究中机器学习应用需求旺盛，但缺乏专业知识的用户易出错。GLEAM提供基于Galaxy的web无代码工具包，标准化数据分区、模型选择、训练评估和报告流程，支持表格、图像和多模态数据。在免疫疗法反应预测、皮肤病变分类和癌症复发预测任务中，GLEAM产出高准确率模型，并显著提升分析透明度和可重复性。
source: biorxiv
selection_source: fresh_fetch
motivation: 降低生物医学研究者使用机器学习的门槛，同时确保最佳实践和高质量结果。
method: 基于Galaxy平台开发GLEAM，实现无代码监督学习，包含标准化数据分区、模型选择、训练、评估和报告模块。
result: 在三个生物医学任务中成功预测，模型准确度高，并改进分析透明度和可重复性。
conclusion: GLEAM使机器学习更易用且更严谨，推动生物医学研究可重复性。
---

## 摘要
机器学习在生物医学研究中日益成为核心，但要充分利用机器学习，通常需要大量的计算专业知识和严谨的方法论，才能产生高质量的结果。为了使生物医学研究人员更容易使用机器学习工具，同时支持最佳实践方法，我们开发了Galaxy学习和建模（GLEAM）软件工具包。GLEAM通过一组基于网络、无需编码的软件工具，使研究人员能够对表格、图像和多模态生物医学数据集进行监督式机器学习分析。GLEAM标准化了数据划分、模型选择、训练、评估和报告，帮助研究人员以更高的严谨性和一致性应用机器学习。GLEAM运行在Galaxy计算工作台上，并利用Galaxy的核心功能，使所有分析都可访问、可重现和可扩展。我们在三个生物医学任务上验证了GLEAM：预测患者对免疫治疗的反应、皮肤病变分类以及癌症复发预测。在这些任务中，GLEAM生成了高精度的预测模型，并提高了透明度、可重复性和严谨性。

## Abstract
Machine learning is increasingly central to biomedical research, but using machine learning well often requires substantial computational expertise and methodological care to produce high-quality results. To make machine learning tools more accessible to biomedical researchers while supporting best-practice approaches, we developed the Galaxy Learning and Modeling (GLEAM) software toolkit. GLEAM enables researchers to perform supervised machine learning analyses through a set of web-based, code-free software tools for tabular, image, and multimodal biomedical datasets. GLEAM standardizes data partitioning, model selection, training, evaluation, and reporting, helping researchers apply machine learning with greater rigor and consistency. GLEAM runs on the Galaxy computational workbench and uses Galaxys core features to make all analyses accessible, reproducible, and scalable. We validated GLEAM on three biomedical tasks: predicting patient response to immunotherapy, skin lesion classification, and cancer recurrence prediction. Across these tasks, GLEAM produced highly accurate predictive models and improved transparency, reproducibility, and rigor.