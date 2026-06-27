---
title: "S4-Driver: Scalable Self-Supervised Driving Multimodal Large Language Model with Spatio-Temporal Visual Representation"
title_zh: S4-Driver：基于时空视觉表示的可扩展自监督驾驶多模态大语言模型
authors: "Xie, Yichen, Xu, Runsheng, He, Tong, Hwang, Jyh-Jing, Luo, Katie, Ji, Jingwei, Lin, Hubert, Chen, Letian, Lu, Yiren, Leng, Zhaoqi, Anguelov, Dragomir, Tan, Mingxing"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Xie_S4-Driver_Scalable_Self-Supervised_Driving_Multimodal_Large_Language_Model_with_Spatio-Temporal_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 用于自动驾驶感知与规划的多模态大语言模型
tldr: 该论文提出S4-Driver，一个可扩展的自监督驾驶多模态大语言模型（MLLM）。它针对现有MLLM在2D图像空间预训练导致3D规划不足的问题，引入时空视觉表示，直接在3D空间学习。S4-Driver无需人类标注即可从传感器输入生成规划轨迹，在nuScenes等数据集上达到与有监督方法相当的性能，为端到端自动驾驶的纯自监督学习提供了新的突破。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1692, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 764, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 770, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 848, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 848, \"height\": 391, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 865, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1576, \"height\": 808, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1589, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 865, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 791, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xie-s4-driver-scalable-self-supervised-driving-multimodal-large-language-model-with-spatio-temporal-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 711, \"height\": 231, \"label\": \"Table\"}]"
motivation: 现有基于MLLM的端到端自动驾驶方法依赖2D预训练，缺乏3D规划能力。
method: 提出S4-Driver，通过时空视觉表示在3D空间进行自监督学习，无需人类标注。
result: 在自动驾驶基准上实现与有监督方法媲美的规划性能。
conclusion: 直接在3D空间自监督预训练可以弥合感知与规划的表示鸿沟。
---

## Abstract
The latest advancements in multi-modal large language models (MLLMs) have spurred a strong renewed interest in end-to-end motion planning approaches for autonomous driving. Many end-to-end approaches rely on human annotations to learn intermediate perception and prediction tasks, while purely self-supervised approaches--which directly learn from sensor inputs to generate planning trajectories without human annotations--often underperform the state of the art. We observe a key gap in the input representation space: end-to-end approaches built on MLLMs are often pretrained with reasoning tasks in 2D image space rather than the native 3D space in which autonomous vehicles plan. To this end, we propose S4-Driver, a scalable self-supervised motion planning algorithm with spatio-temporal visual representation, based on the popular PaLI multimodal large language model. S4-Driver uses a novel sparse volume strategy to seamlessly transform the strong visual representation of MLLMs from perspective view to 3D space without the need to finetune the vision encoder. This representation aggregates multi-view and multi-frame visual inputs and enables better prediction of planning trajectories in 3D space. To validate our method, we run experiments on both nuScenes and Waymo Open Motion Dataset (with in-house camera data). Results show that S4-Driver performs favorably against existing supervised multi-task approaches while requiring no human annotations. It also demonstrates great scalability when pretrained on large volumes of unannotated driving logs.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义
- **研究动机**：当前基于多模态大语言模型（MLLM）的端到端自动驾驶规划方法大多依赖2D图像空间的预训练，难以直接进行3D空间中的运动规划；同时，有监督方法需要大量人工标注，而纯自监督方法性能落后。
- **核心目标**：提出一种可扩展的自监督运动规划算法，无需人类标注即可从原始传感器输入直接预测3D轨迹，并利用海量未标注驾驶日志进行预训练。
- **整体含义**：弥合MLLM在2D视觉预训练与3D规划任务之间的表示鸿沟，推动自监督端到端自动驾驶的发展。

## 2. 论文提出的方法论
- **核心思想**：基于PaLI系列MLLM，设计一种稀疏体积表示（Sparse Volume Representation）将多视角、多帧图像特征从透视视图无缝转换到3D空间，增强模型的3D时空推理能力；同时引入层次规划与多解码聚合机制提升规划性能。
- **关键技术细节**：
  - **稀疏体积表示**：对每个体素，通过轻量投影从多视图特征图中双线性采样并平均得到语义特征，再与可学习位置编码相加；引入门控机制（gate）自适应选择与规划相关的稀疏体素，并使用可学习空特征表示无关区域，减少计算量。
  - **局部特征聚合**：在MLLM自注意力中引入基于3D相对位置偏差的偏置项，促进局部信息在体素间的聚合。
  - **多帧时间融合**：将历史多帧图像分别构建特征体积，经自车运动补偿后拼接并通过全连接层融合，捕捉时序动态。
  - **层次规划**：先预测元决策（保持静止、匀速、加速、减速），再基于元决策生成具体轨迹，无需额外标注（元决策标签由启发式规则自动生成）。
  - **多解码投票**：使用核采样生成多个候选轨迹，简单平均得到最终轨迹，缓解模型对简单行为的偏好偏差。
- **算法流程**（文字说明）：
  1. 输入多帧多视角图像、历史自车状态和高级行为命令。
  2. 用冻结的ViT编码器提取2D特征，构建稀疏3D体积特征（含门控选择与时间融合）。
  3. 体积特征与文本令牌（历史状态、命令）一同送入多模态编码器-解码器，其中自注意力引入3D相对位置偏置。
  4. 解码器首先输出元决策，再基于元决策输出未来轨迹文本。
  5. 通过核采样多次解码并平均得到最终规划轨迹。

## 3. 实验设计
- **数据集**：
  - **nuScenes**：1k序列，5.5小时，2Hz，规划3秒轨迹。
  - **WOMD-Planning-ADE**：基于Waymo Open Motion Dataset构建，103k序列，574小时，10Hz，规划5秒轨迹，包含8个摄像头图像及6种高级行为命令；并提出行为均衡的bADE指标。
- **Benchmark对比**：
  - 多任务端到端方法：UniAD、VAD、PARA-Drive。
  - MLLM方法：GPT-Driver、DriveVLM、OmniDrive。
  - 自监督方法：DriveVLM (w/o CoT)。
  - 也对比了以高质量物体轨迹和路图作为输入的模块化方法MotionLM。
- **主要结果**：
  - **nuScenes**：S4-Driver（无额外数据）在Avg L2误差0.38m，优于大多数有监督方法；经过WOMD预训练后Avg L2 0.31m，优于所有对比方法。
  - **WOMD-Planning-ADE**：S4-Driver在行为均衡指标bADE@5s达到0.928，优于Vanilla PaLI（1.069）和MotionLM（0.978）。

## 4. 资源与算力
- **明确说明**：在128块Google Cloud TPU v4上训练约2.5天，使用batch size 256，学习率3e-3。ViT编码器冻结，仅微调插入模块和多模态编码器-解码器。

## 5. 实验数量与充分性
- **实验组数**：包含主对比实验（两个数据集）、多组消融实验（模型输入、稀疏体积分辨率、MLLM规模、训练数据规模）、可扩展性实验（不同数据量）、定性结果可视化及元决策准确性、稀疏体积分布分析。
- **充分性与公平性**：
  - 消融实验覆盖关键模块（输入、体积表示、时间融合、多解码、预训练等），对比基线（Vanilla PaLI、低分辨率体积等）合理。
  - 在WOMD上专门设计行为均衡指标bADE，避免简单场景主导评估，更客观。
  - 与有监督方法公平比较（均使用相同数据集，且标注情况明确标注）。
  - 不足之处：未在闭环模拟或真实路测中验证；未与最新MLLM如Gemini（EMMA）直接对比（EMMA未出现在论文中，可能稍晚）。

## 6. 论文的主要结论与发现
- 自监督MLLM规划方法可以仅依赖自车轨迹监督，达到甚至超越有监督多任务方法的性能。
- 稀疏体积表示有效增强了MLLM的3D时空推理，对规划性能提升显著。
- 随着训练数据规模增大（从20k到400k），S4-Driver性能持续提升，展示了良好的可扩展性。
- 层次规划（元决策）和多解码投票是简单有效的“免费午餐”，无需额外标注即可提升规划准确性。

## 7. 优点
- **方法创新性**：提出稀疏体积表示结合门控机制，在不微调视觉编码器前提下将MLLM特征提升到3D空间，并保留预训练知识。
- **自监督与可扩展性**：完全不需要人类标注，可充分利用海量未标注驾驶日志，实际部署成本低。
- **评估全面**：提出行为均衡指标bADE，更公平评估算法在长尾场景的表现。
- **实验严谨**：在nuScenes和WOMD两个大规模数据集上进行，消融实验充分，对比基线包括多种有监督方法，结果可信。

## 8. 不足与局限
- **依赖高级行为命令**：需要导航系统提供驾驶命令，可能限制在无导航情况下的应用。
- **仅开放环路评估**：实验均为离线开环评估，未在闭环模拟或真实车辆上测试，无法反映实际交互鲁棒性。
- **模型与计算开销**：基于PaLI3-5B，训练需128块TPU v4约2.5天，资源需求较高。
- **稀疏体积的启发式选择**：门控学习依赖于隐式优化，可能在某些复杂场景下选择不充分。
- **未与其他大规模MLLM（如Gemini）公平比较**：文中EMMA为后续工作，但未直接进行实验对比。

（完）
