---
title: "Feature4X: Bridging Any Monocular Video to 4D Agentic AI with Versatile Gaussian Feature Fields"
title_zh: Feature4X：将任意单目视频桥接至4D智能体AI
authors: "Zhou, Shijie, Ren, Hui, Weng, Yijia, Zhang, Shuwang, Wang, Zhen, Xu, Dejia, Fan, Zhiwen, You, Suya, Wang, Zhangyang, Guibas, Leonidas, Kadambi, Achuta"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhou_Feature4X_Bridging_Any_Monocular_Video_to_4D_Agentic_AI_with_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 4.0
evidence: 将2D视觉模型扩展到4D，支持开放词汇分割
tldr: 针对3D/4D场景中视觉语言任务缺乏大规模标注数据的问题，本文提出Feature4X框架，利用高斯特征场将2D视觉基础模型功能扩展到4D领域，仅需单目视频即可实现开放词汇分割、语言引导编辑等操作。该方法大幅降低了对多视图数据的需求，为4D场景理解提供了通用解决方案。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1794, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1805, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 845, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 818, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1763, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1524, \"height\": 763, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 864, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-feature4x-bridging-any-monocular-video-to-4d-agentic-ai-with-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 238, \"label\": \"Table\"}]"
motivation: 3D/4D场景缺乏大规模标注数据，限制视觉语言任务泛化，亟需从2D模型高效迁移的方法。
method: 构建高斯特征场，从单目视频中学习4D表示，将2D基础模型能力扩展到4D。
result: 在开放词汇分割和语言引导编辑任务上达到先进水平，无需多视图数据。
conclusion: 高斯特征场是连接2D与4D视觉语言能力的有效桥梁，推动了智能体AI的发展。
---

## Abstract
Recent advancements in 2D and multimodal models have achieved remarkable success by leveraging large-scale training on extensive datasets. However, extending these achievements to enable free-form interactions and high-level semantic operations with complex 3D/4D scenes remains challenging. This difficulty stems from the limited availability of large-scale, annotated 3D/4D or multi-view datasets, which are crucial for generalizable vision and language tasks such as open-vocabulary and prompt-based segmentation, language-guided editing, and visual question answering (VQA). In this paper, we introduce Feature4X, a universal framework designed to extend any functionality from 2D vision foundation model into the 4D realm, using only monocular video input, which is widely available from user-generated content. The "X" in Feature4X represents its versatility, enabling any task through adaptable, model-conditioned 4D feature field distillation. At the core of our framework is a dynamic optimization strategy that unifies multiple model capabilities into a single representation. Additionally, to the best of our knowledge, Feature4X is the first method to distill and lift the features of video foundation models (e.g. SAM2, InternVideo2) into an explicit 4D feature field using Gaussian Splatting. Our experiments showcase novel view segment anything, geometric and appearance scene editing, and free-form VQA across all time steps, empowered by LLMs in feedback loops. These advancements broaden the scope of agentic AI applications by providing a foundation for scalable, contextually and spatiotemporally aware systems capable of immersive dynamic 4D scene interaction.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：2D视觉和多模态模型在大规模数据集上取得了巨大成功，但将其扩展到3D/4D场景的自由交互和高层语义操作（如开放词汇分割、语言引导编辑、视觉问答）面临挑战。根本原因是缺乏大规模标注的3D/4D或多视图数据集。
- **整体含义**：本文提出Feature4X，一种通用框架，旨在仅利用广泛可获取的单目视频输入，将任意2D视觉基础模型的功能扩展到4D领域。通过构建统一的4D特征场，桥接2D模型与4D场景，推动4D智能体AI的发展。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：基于动态3D高斯溅射（3DGS）的4D场景表示，为每个高斯附加统一潜在特征，蒸馏多种2D基础模型的特征，支持多种下游任务（分割、编辑、VQA）。
- **关键技术细节**：
  - 采用MoSca的4D运动支架（Motion Scaffold）结构表示动态场景，包含节点集 \(V\)（编码运动轨迹和潜在特征\(h_i\)）和边集\(E\)（k近邻图）。
  - 每个3D高斯的特征\(f_j\)通过插值其K近邻支架节点的特征得到：\(f_j = \sum_{i\in\mathcal{E}(i^*)} w_i h_i\)，实现紧凑特征表示（参数减少约100倍）。
  - 使用并行N维高斯光栅化器，同时渲染RGB图像和统一潜在特征图\(\hat{\mathbf{F}}\)，然后通过轻量级解码器\(D_s\)解码为任务特定特征\(\hat{\mathbf{F}}^s\)。
  - 训练损失：光度损失（来自MoSca）+ 特征损失 \(\mathcal{L}_{\text{feat}} = \sum_s \text{MSE}(\hat{\mathbf{F}}^s_\tau, \mathbf{F}^s_\tau)\)，其中\(\mathbf{F}^s_\tau\)来自预训练2D模型（如SAM2、CLIP-LSeg、InternVideo2）的特征。
  - 与LLM（GPT-4o）集成：LLM解析用户自然语言提示，自动优化编辑参数（如阈值），迭代细化结果，形成感知-推理-动作循环。

## 3. 实验设计

- **数据集与场景**：
  - **Nvidia动态场景数据集**：用于定量评估语义分割性能（PSNR、mIoU、准确率、内存）。
  - **DAVIS数据集**：50个场景，构建400个客观问题，评估时空VQA（空间、时间、时空准确率）。
  - **真实世界视频**：多段单目视频（如动物、物体运动），用于定性展示分割、编辑、VQA。
- **基准方法对比**：
  - 语义分割：对比MoSca（基线4D重构）和MoSca+Feature3DGS（朴素非紧致基线）。
  - VQA：对比输入视频视图、局部/全局新视图、局部/全局新特征等多种推理源。
- **评估指标**：PSNR（重构质量）、mIoU与准确率（分割）、内存大小（MB）、推理时间（秒）、VQA准确率。

## 4. 资源与算力

- **未明确说明**：论文正文未提及使用的GPU型号、数量、训练总时长。仅在实验部分报告了推理时间（如表2中全局新特征推理12.24秒，表3中全局新特征推理2.81秒），但训练阶段的算力细节缺失。

## 5. 实验数量与充分性

- **实验数量**：
  - 定量实验：表1（Nvidia数据集语义分割）、表2（单场景VQA不同推理源对比）、表3（DAVIS数据集VQA总体结果）。
  - 定性实验：图3（SAM2分割）、图5（CLIP语义分割）、图6（场景编辑）、图7（VQA示例）。
  - 消融研究：对比单CLIP头与全模型（表1），证明紧凑表示有效；对比不同推理源（表2、表3），验证4D特征场优势。
- **充分性与公平性**：
  - 实验覆盖2D（分割）、3D（编辑）、4D（VQA）任务，场景多样。
  - 对比方法合理，MoSca和Feature3DGS均为强基线。
  - 不足之处：DAVIS仅50场景400问题，规模偏小；缺少对长视频、复杂遮挡场景的系统评估；未报告训练/推理的完整计算开销。

## 6. 主要结论与发现

- Feature4X可在保持重构质量（PSNR相当）的同时，大幅降低内存占用（约6.2倍于MoSca+Feature3DGS）。
- 通过4D特征场，直接解码SAM2特征，避免了RGB渲染伪影干扰，加速推理约4倍，并实现时空一致的任意视角分割。
- 在时空VQA中，利用全局新视图特征相比输入视频视图，准确率提升（总体61.32% vs 49.06%），推理速度提高约3倍。
- 首次将视频基础模型（SAM2、InternVideo2）特征蒸馏到4D高斯场，验证了紧凑表示的通用性。

## 7. 优点（方法或实验设计亮点）

- **方法创新**：首次实现动态4D特征场蒸馏，支持2D模型功能迁移；紧凑支架特征表示有效降低参数和内存。
- **多任务统一**：单一4D表示同时支持分割、编辑、VQA，无需为每个任务单独训练。
- **LLM智能体集成**：实现自然语言驱动的自适应编辑，自动调参并迭代优化，降低人工干预。
- **全面实验验证**：覆盖2D/3D/4D任务，定量定性结合，并与强基线对比，证明有效性和效率。

## 8. 不足与局限

- **算力细节缺失**：论文未报告训练所需GPU型号、数量、时长，影响可复现性和实际部署评估。
- **VQA评估规模有限**：仅用DAVIS 50场景400问题，且问题由作者构建，可能引入偏差；缺乏公开VQA基准对比。
- **编辑效果依赖特征对齐**：CLIP特征与高斯特征的相似度计算可能导致不完美编辑（如颜色改变不精确），需依赖LLM迭代补偿。
- **重构质量依赖MoSca**：4D场景重构质量受限于MoSca的精度，在复杂动态场景（大形变、严重遮挡）下可能退化。
- **缺乏与更多4D方法的对比**：未见与4D-VQA、4D编辑等相关工作的直接比较（如与NeRF-based方法对比）。

（完）
