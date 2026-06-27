---
title: "g3D-LF: Generalizable 3D-Language Feature Fields for Embodied Tasks"
title_zh: g3D-LF：用于具身任务的通用3D语言特征场
authors: "Wang, Zihan, Lee, Gim Hee"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_g3D-LF_Generalizable_3D-Language_Feature_Fields_for_Embodied_Tasks_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 用于具身任务的通用3D语言特征场
tldr: 现有具身任务中的3D表示缺乏语言交互能力，且难以泛化。本文提出g3D-LF，一种在大规模3D语言数据集上预训练的通用3D语言特征场模型，能够处理智能体输入的RGB-D图像，编码包含语义和空间关系的特征场，支持新视角预测、BEV地图生成和多粒度语言查询。该表示可泛化到未见环境，实现实时构建和动态更新。实验表明，g3D-LF在多种具身理解任务上取得优异性能，为语言引导的3D感知提供了强大基础。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 929, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 439, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 923, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 912, \"height\": 542, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 892, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 906, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 744, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 882, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-g3d-lf-generalizable-3d-language-feature-fields-for-embodied-tasks-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 105, \"label\": \"Table\"}]"
motivation: 现有方法缺乏可泛化的3D语言特征表示，难以支持智能体进行实时场景理解与语言交互。
method: 提出g3D-LF，利用体积渲染和多尺度编码器从RGB-D图像中学习语义与空间融合的3D语言特征场。
result: 在多个具身任务上取得领先性能，且能实时构建和动态更新。
conclusion: g3D-LF为语言引导的3D感知提供了高效可泛化的解决方案。
---

## Abstract
We introduce Generalizable 3D-Language Feature Fields (g3D-LF), a 3D representation model pre-trained on large-scale 3D-language dataset for embodied tasks. Our g3D-LF processes posed RGB-D images from agents to encode feature fields for: 1) Novel view representation predictions from any position in the 3D scene; 2) Generations of BEV maps centered on the agent; 3) Querying targets using multi-granularity language within the above-mentioned representations. Our representation can be generalized to unseen environments, enabling real-time construction and dynamic updates. By volume rendering latent features along sampled rays and integrating semantic and spatial relationships through multiscale encoders, our g3D-LF produces representations at different scales and perspectives, aligned with multi-granularity language, via multi-level contrastive learning. Furthermore, we prepare a large-scale 3D-language dataset to align the representations of the feature fields with language. Extensive experiments on Vision-and-Language Navigation under both Panorama and Monocular settings, Zero-shot Object Navigation, and Situated Question Answering tasks highlight the significant advantages and effectiveness of our g3D-LF for embodied tasks. Our source code and dataset will be made open-source upon paper acceptance.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：g3D-LF: Generalizable 3D-Language Feature Fields for Embodied Tasks

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有用于具身任务的3D场景表示方法（如特征场模型）存在以下关键缺陷：
  - 监督信号来自2D基础模型（如CLIP、DINOv2），缺乏对3D空间关系的理解；
  - 训练时无语言监督，导致与语言语义存在显著鸿沟；
  - 大规模表示（如全景图、BEV图）难以处理长文本理解。
- **整体含义**：本文旨在构建一种**可泛化的3D语言特征场**，使得智能体能够从RGB-D图像中实时构建3D表示，并通过多粒度语言进行查询，从而提升在未知环境中的导航、问答等具身任务性能。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 设计**g3D-LF**模型，在大型3D语言数据集上预训练，将多尺度3D表示（新视角特征图、全景图、BEV图）与多粒度语言对齐，支持实时构建和动态更新。

### 关键技术细节
1. **特征场编码**：
   - 输入：带位姿的RGB-D图像 → CLIP图像编码器提取细粒度特征 → 结合深度图映射到3D世界坐标，形成特征点集合，并存储方向角和区域尺寸。
   - 特征点集在线更新：`M_t = M_{t-1} ∪ {[g_{t,i}, P_{t,i}, θ_{t,i}, s_{t,i}]}`。

2. **射线-视图-全景编码**：
   - 使用MLP函数聚合k近邻特征点，预测任意点的语义表示`r`和体密度`σ`。
   - 新视角渲染：对每条射线采样N个点，通过体渲染公式合成子区域特征`R(u,v)`；经Transformer视图编码器获得新视角表示`V'`。
   - 全景编码：预测12个新视角（间隔30°），经全景编码器得到`{V''_i}`。

3. **射线-BEV编码**：
   - 渲染射线从天花板向下垂直发射，通过MLP BEV网络聚合特征点，体渲染得到BEV特征图`ˆR`（覆盖16.8m×16.8m区域），再经下采样和Transformer编码器得到`ˆR'`。

4. **多层级对比学习**：
   - **平衡对象级对齐**：使用包含1883类室内物体的词汇表，对射线表示进行对比学习，并对前10%高交叉熵的射线增加权重（α因子），缓解长尾分布。
   - **细粒度对比学习（长文本）**：将BEV局部窗口（5×5）与长文本词特征通过亲和矩阵计算相似度，取Top-L（词数）平均作为细粒度相似度，进行对比学习。
   - **CLIP知识蒸馏**：使用真实新视图/区域图像的CLIP特征，对新视角、全景、BEV表示进行对比监督，确保泛化能力。

## 3. 实验设计

### 数据集与场景
- **3D语言预训练数据**：约5K室内场景（ScanNet、HM3D、Structured3D），近100万语言标注（来自SceneVerse + 人工标注的物体引用）。
- **下游任务测评数据集**：
  - **视觉语言导航(VLN)**：R2R-CE（基于Matterport3D，Habitat模拟器），含5,611条轨迹，每条3条英文指令，平均路径长度9.89米。
  - **零样本目标导航**：HM3D验证集（2,000 episodes，6类物体）和MP3D验证集（2,195 episodes，21类物体）。
  - **情景问答(SQA)**：SQA3D（基于ScanNet，20.4k描述，33.4k问题）。

### Benchmark与对比方法
- **VLN（单目）**：对比CM2、WS-MGMap、NaVid、InstructNav、VLN-3DFF等（表1）。
- **VLN（全景）**：对比Sim2Sim、VLN-BERT、GridMM、DREAM、HNR、Energy等（表2）。
- **零样本目标导航**：对比ZSON、ESC、VLFM、InstructNav、GAMap、SG-Nav等（表3）。
- **情景问答**：对比ClipBERT、ScanQA、SQA3D、3D-VisTA、SceneVerse、LEO、Scene-LLM等（表4）。

## 4. 资源与算力

- 预训练配置：**2块 RTX 6000 Ada GPU**，训练约 **50K episodes**，耗时约 **10天**。
- 推理速度：新视角体积渲染 73.6 FPS，全景 5.9 FPS，BEV 6.3 FPS（单RTX 4090），可实现实时推理。

## 5. 实验数量与充分性

- **主实验**：4个表格（表1-4），覆盖VLN单目、VLN全景、零样本目标导航、情景问答四个任务，每个任务均对比多个SOTA方法。
- **消融实验**：表5（模块消融：新视角/全景 vs BEV）、表6（对比学习策略消融：对象级、CLIP蒸馏、细粒度对比、平衡损失）。共2个消融表，覆盖关键设计。
- **运行时分析**：表7，详细测量各模块FPS。
- **充分性评估**：
  - 实验组数较多，跨不同任务和设置，验证了方法的通用性。
  - 消融实验设计合理，逐一检验各模块和损失函数的影响。
  - 对比方法选取得当，包括LLM方法、VLM方法、特征场方法，具有客观性。
  - 唯一潜在不足：HM3D零样本任务中，由于预训练数据包含了HM3D训练场景，并非严格零样本，但同时在MP3D上验证了泛化性（未使用其训练场景）。

## 6. 主要结论与发现

- g3D-LF在单目VLN任务上取得显著提升（SR 46.3% vs 基线VLN-3DFF 43.7%），在全景VLN上SPL达到SOTA（52%）。
- 零样本目标导航中：在HM3D上SR 55.6%，在MP3D上SR 39.0%，超越大多数方法，且是唯一使用特征场而非VLM的方法。
- 情景问答中：定位性能（Acc@0.5m 23.4%，Acc@15° 29.8%）优于纯图像输入方法，但问答准确率低于使用点云或LLM的方法。
- 预训练至关重要：无预训练时VLN性能大幅下降。
- CLIP蒸馏和语言监督缺一不可，且细粒度对比学习显著提升长文本理解。
- 平衡对象级对齐有效缓解长尾物体识别问题。

## 7. 优点（方法或实验设计亮点）

- **创新性**：首次将大规模3D语言数据用于通用特征场预训练，实现多尺度3D表示与多粒度语言的对齐。
- **实用性**：支持实时构建和在线更新（推理速度快），适用于真实机器人场景。
- **模块化设计**：新视角、全景、BEV三种表示可单独或组合使用，灵活适配不同任务。
- **全面消融**：验证了每种损失函数和模块的必要性，实验设计严谨。
- **公平对比**：在VLN、零样本导航等任务中，基于已有基线（如VLN-3DFF、HNR、VLFM）进行公平替换，保证了对比的公平性。
- **开源**：代码和数据集将公开，可复现。

## 8. 不足与局限

- **动态环境限制**：无法适应物体/人物移动的动态场景（仅支持静态场景）。
- **任务覆盖不全**：未评估操作任务（如物体操纵），且未与LLM结合进行文本生成。
- **数据质量与规模**：3D语言数据量（百万级）远小于图像语言数据（数十亿级），限制了模型的语义泛化上限。
- **情景问答精度有限**：仅使用图像作为输入，未使用低噪声点云，因此在问答准确率（EM@1 47.7%）上低于使用点云+LLM的方法（如Scene-LLM 54.2%）。
- **严格零样本性存疑**：HM3D零样本导航任务中，预训练数据包含了对应的训练场景，可能引入数据泄露；但在MP3D上的结果证明了泛化性。

（完）
