---
title: Distilling Multi-modal Large Language Models for Autonomous Driving
title_zh: 为自动驾驶蒸馏多模态大语言模型
authors: "Hegde, Deepti, Yasarla, Rajeev, Cai, Hong, Han, Shizhong, Bhattacharyya, Apratim, Mahajan, Shweta, Liu, Litian, Garrepalli, Risheek, Patel, Vishal M., Porikli, Fatih"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Hegde_Distilling_Multi-modal_Large_Language_Models_for_Autonomous_Driving_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 将多模态大模型知识蒸馏到基于视觉的自动驾驶规划器
tldr: 大语言模型作为规划器计算成本高，本文提出DiMA，通过设计代理任务将多模态LLM的世界知识蒸馏到纯视觉端到端规划器中，实现无LLM推理的高效规划。联合训练使场景编码器学习结构化表示，在长尾场景下保持了LLM的泛化能力且推理更快。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 829, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1608, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 693, \"height\": 713, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1805, \"height\": 559, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1802, \"height\": 1049, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 871, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1811, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-hegde-distilling-multi-modal-large-language-models-for-autonomous-driving-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 420, \"label\": \"Table\"}]"
motivation: 使用LLM做规划器测试时计算代价高。
method: 通过代理任务将多模态LLM知识蒸馏到视觉端到端规划器。
result: 在保持泛化能力的同时显著降低推理成本。
conclusion: 知识蒸馏可实现高效且鲁棒的自动驾驶规划。
---

## Abstract
Autonomous driving demands safe motion planning, especially in critical "long-tail" scenarios. Recent end-to-end autonomous driving systems leverage large language models (LLMs) as planners to improve generalizability to rare events. However, using LLMs at test time introduces high computational costs. To address this, we propose DiMA, an end-to-end autonomous driving system that maintains the efficiency of an LLM-free (or vision-based) planner while leveraging the world knowledge of an LLM. DiMA distills the information from a multi-modal LLM to a vision-based end-to-end planner through a set of specially designed surrogate tasks. Under a joint training strategy, a scene encoder common to both networks produces structured representations that are semantically grounded as well as aligned to the final planning objective. Notably, the LLM is optional at inference, enabling robust planning without compromising on efficiency. Training with DiMA results in a 37% reduction in the L2 trajectory error and an 80% reduction in the collision rate of the vision-based planner, as well as a 44% trajectory error reduction in long-tail scenarios. \ours also achieves state-of-the-art performance on the nuScenes planning benchmark.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：自动驾驶中，端到端规划器在“长尾场景”（罕见、复杂的驾驶情况）下表现不佳。近期工作引入大语言模型（LLM）作为规划器，借助其世界知识提升泛化能力，但LLM推理时计算开销巨大，限制了实际部署。
- **目标**：在保持纯视觉规划器高效性的前提下，充分吸收多模态大语言模型（MLLM）的世界知识，获得既鲁棒又高效的规划系统。
- **整体含义**：本文提出一种新颖的知识蒸馏框架DiMA，将MLLM的知识通过结构化场景表示和精心设计的代理任务迁移到纯视觉规划器中，推理时无需LLM参与，从而实现性能与效率的平衡。

## 2. 方法论

### 核心思想
- 联合训练一个纯视觉端到端规划器（vision-based planner）和一个多模态大语言模型（MLLM），通过蒸馏和代理任务使视觉规划器学习到语义丰富且与规划目标对齐的场景表示。
- 推理时仅使用视觉规划器，MLLM可被丢弃，保持高效率；视觉规划器也可可选地保留MLLM进行语言推理。

### 关键技术细节

#### 视觉规划器（Vision-based Planner）
- 架构：场景编码器（Scene Encoder）+ 规划变换器（Planning Transformer）。
- 场景编码器将多视图图像序列编码为结构化的**BEAM** token嵌入（Bird’s-Eye-View, Ego, Agent, Map），显式建模场景组件。
- 规划变换器基于BEAM token预测未来轨迹。

#### 多模态大语言模型（MLLM）
- 输入：视觉规划器产生的BEAM token嵌入，通过组件特定的Q-former适配器压缩为固定长度序列后送入LLM（基于LLaVA-v1.5-7B）。
- 训练任务包括：
  1. **视觉问答（VQA）**：基于场景问题和BEAM token回答感知、预测、规划相关问题。
  2. **规划预测**：MLLM中有独立规划解码头预测轨迹。
  3. **代理任务（Surrogate Tasks）**：
     - **掩码token重建**：随机掩蔽部分BEV token，让MLLM重构。
     - **未来BEV预测**：预测未来2帧的BEV token。
     - **场景编辑**：在场景中增删车辆，构造对应的问答对和规划标签，迫使模型学习交互。
  4. **蒸馏损失（Distillation）**：最小化MLLM和视觉规划器在规划头层前特征的KL散度（针对ego token）。

#### 公式与算法流程
- 总损失：
  \[
  \mathcal{L} = \mathcal{L}_{\text{planning}} + \mathcal{L}_{\text{LLM}} + \mathcal{L}_{\text{recon}} + \mathcal{L}_{\text{future}} + \mathcal{L}_{\text{distill}}
  \]
- 训练两阶段：
  1. 预训练纯视觉规划器60个epoch（感知、预测、规划）。
  2. 联合训练视觉规划器和MLLM 30个epoch（LLM使用LoRA微调）。

## 3. 实验设计

### 数据集与场景
- **nuScenes**：28k样本（22k训练/6k验证），提供3D框、速度、CAN总线轨迹等。
- **VQA监督**：使用DriveLM（4k样本，300k QA对）；对无标注样本用Llama3-70B生成补充QA，行为QA用规则生成。
- **评估拆分**：
  - 完整验证集（6019样本）
  - “targeted”子集（689个转弯场景）[48]
  - 长尾场景（3点转弯、从停止恢复、超车）[38]

### 基准与对比方法
- **标准化评估[48]**：与UniAD、VAD-Base、PARA-Drive、TOKEN、AD-MLP、PARA-Drive+对比。
- **VAD评估[20]**：与ST-P3、UniAD、VAD-Tiny/Base、VLP-VAD-Base、OmniDrive、DriveVLM、DriveVLM-Dual等对比。

## 4. 资源与算力

- **论文未明确说明使用的GPU型号、数量或具体训练时长**。仅提及训练机制（预训练60 epoch + 联合训练30 epoch），LLM用LoRA微调，但未提供硬件细节。
- 从模型规模推断：MLLM使用LLaVA-v1.5-7B（7B参数），但未报告实际计算成本。

## 5. 实验数量与充分性

### 实验组数量
- **标准化评估**：10种方法对比（含DiMA多个变体），涵盖完整集和targeted集。
- **VAD评估**：12种方法对比（含DiMA变体、MLLM分支、DiMA-Dual）。
- **长尾评估**：3个场景（点转弯零样本、恢复、超车），对比4-5种方法。
- **消融实验**：8组（ID-1至ID-8），逐步加入BEAM token、蒸馏、三个代理任务。

### 公平性与客观性
- 采用标准化评估[48]消除过去评估不一致（如时间平均方式、BEV离散化差异），保证公平。
- 对比方法包含近期SOTA（TOKEN、PARA-Drive、DriveVLM等），且DiMA均取得最佳或次佳。
- 消融实验控制变量，系统验证各组件贡献。

**结论：实验数量充足，设计合理，对比公平，结论可信。**

## 6. 主要结论与发现

- 训练DiMA后，视觉规划器的**L2轨迹误差降低37%**，**碰撞率降低80%**，**长尾场景误差降低44%**。
- 在nuScenes规划基准上达到**SOTA**（标准化评估和VAD评估均优于先前方法）。
- 推理时MLLM可选，DiMA-Dual（混合推理）进一步提升性能（例如VAD-Tiny变体匹配VAD-Base性能）。
- 代理任务（掩码重建、未来预测、场景编辑）均有效，逐步加入带来持续改进。
- 结构化场景表示（BEAM token）比简单使用BEV token更有效。

## 7. 优点

- **创新蒸馏框架**：首次将MLLM知识系统性地蒸馏到视觉规划器，实现高效推理。
- **结构化输入**：BEAM token显式建模场景组件，比稠密token更利于MLLM理解。
- **丰富的代理任务**：掩码重建、未来预测、场景编辑针对规划目标设计，有效提升表示质量。
- **两阶段训练**：先预训练视觉规划器，再联合微调，稳定且有效。
- **推理灵活**：支持纯视觉（高效）或MLLM辅助（高精度）两种模式。
- **实验充分**：在多个评估标准、多个数据集拆分下验证，消融实验清晰。

## 8. 不足与局限

- **未报告计算资源**：缺少GPU型号、数量、训练时间等细节，影响复现和资源评估。
- **仅基于nuScenes**：单数据集验证，泛化性有待在其他数据集（如Waymo、CARLA）验证。
- **场景编辑依赖额外构造**：合成新agent的方式可能引入偏差，且未在真实罕见场景中验证。
- **未进行闭环评估**：所有实验为开环（基于历史真实轨迹），实际闭环性能未知。
- **MLLM分支性能低于混合模型**：单独使用MLLM规划头效果不如蒸馏后的视觉规划器，说明蒸馏损失可能压缩了部分知识。
- **长尾场景数量有限**：仅3类手工筛选事件，覆盖不全面。

（完）
