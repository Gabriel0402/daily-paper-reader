---
title: "ReferSplat: Referring Segmentation in 3D Gaussian Splatting"
title_zh: ReferSplat：3D高斯泼溅中的指代分割
authors: "Shuting He, Guangquan Jie, Changshuo Wang, Yun Zhou, Shuming Hu, Guanbin Li, Henghui Ding"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=reuShgiHdg"
tags: ["query:mmseg"]
score: 8.0
evidence: 利用语言在3D场景中进行多模态指代分割
tldr: 本文提出新的3D指代分割任务R3DGS，并构建Ref-LERF数据集。现有方法在3D多模态理解方面存在挑战。作者提出ReferSplat框架，显式建模空间关系和物体属性，实现基于自然语言描述的3D场景分割。实验证明该方法有效处理遮挡和视角变化，为具身智能的3D环境理解提供关键能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 838, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 818, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-reushgihdg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1741, \"height\": 1025, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 824, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 796, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 852, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-reushgihdg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 860, \"height\": 288, \"label\": \"Table\"}]"
motivation: 3D场景中根据语言描述分割目标物体是具身智能的重要能力，但现有研究不足。
method: 提出ReferSplat框架，结合语言描述和3D高斯特征进行显式空间关系建模。
result: 在Ref-LERF数据集上，ReferSplat在指代分割任务上取得优异效果。
conclusion: 该工作推动了3D多模态理解在具身智能中的应用。
---

## Abstract
We introduce Referring 3D Gaussian Splatting Segmentation (R3DGS), a new task that aims to segment target objects in a 3D Gaussian scene based on natural language descriptions, which often contain spatial relationships or object attributes. This task requires the model to identify newly described objects that may be occluded or not directly visible in a novel view, posing a significant challenge for 3D multi-modal understanding. Developing this capability is crucial for advancing embodied AI. To support research in this area, we construct the first R3DGS dataset, Ref-LERF. Our analysis reveals that 3D multi-modal understanding and spatial relationship modeling are key challenges for R3DGS. To address these challenges, we propose ReferSplat, a framework that explicitly models 3D Gaussian points with natural language expressions in a spatially aware paradigm. ReferSplat achieves state-of-the-art performance on both the newly proposed R3DGS task and 3D open-vocabulary segmentation benchmarks. Dataset and code are available at https://github.com/heshuting555/ReferSplat.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有3D高斯泼溅（3D Gaussian Splatting, 3DGS）领域的研究大多局限于固定类别的开放词汇分割，无法处理基于自由形式自然语言表达（如空间关系、物体属性）的细粒度目标分割。论文提出一个新的任务——**Referring 3D Gaussian Splatting Segmentation (R3DGS)**，要求模型在3D高斯场景中根据自然语言描述（例如“桌子右侧的红色杯子”）分割对应的物体，即使该物体在给定视角下被遮挡或不可见。
- **研究动机**：具身智能（Embodied AI）、自动驾驶、VR/AR等应用需要3D场景与自然语言的灵活交互，现有方法缺乏针对复杂语言表达（包含空间关系）的3D多模态理解能力。
- **整体意义**：R3DGS任务填补了3DGS在语言引导指代分割方面的空白，为3D场景理解提供了更接近人类交互的范式，并为后续研究提供了首个基准数据集 Ref-LERF 和基线方法 ReferSplat。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将自然语言表达与3D高斯点显式建模为**空间感知范式**，通过为每个高斯点分配一个“引用特征向量”，构建 **3D高斯引用场（3D Gaussian Referring Fields）**，直接在高斯点级别计算与文本的相似度，并通过光栅化输出分割掩码。

### 关键技术细节
1. **3D高斯引用场构建**  
   - 为每个高斯点 \(g_i\) 增加引用特征 \(f_{r,i} \in \mathbb{R}^{d_r}\)。  
   - 利用文本编码器（BERT）提取句子特征 \(f_e\) 和词特征 \(f_w\)。  
   - 计算每个高斯点与文本的相似度：  
     \[
     m_i = \sum_j f_{r,i} \times f_{w,j}
     \]  
     其中 \(j\) 遍历句子中的每个词。  
   - 通过光栅化（类似3DGS的alpha混合）将相似度 \(m_i\) 渲染为2D掩码 \(M(v)\)。

2. **伪掩码生成（Pseudo Mask Generation）**  
   - 使用 Grounded SAM 对每个（图像，描述）对生成K个候选掩码及置信度 \(\gamma\)。  
   - 提出**置信度加权IoU策略**：计算每个候选掩码的加权重叠分数 \(p_k\)，选取最高的作为伪地面真值。  
     \[
     p_k = \sum_{j=1}^K \frac{\gamma_k \hat{M}_k \cap \gamma_j \hat{M}_j}{\gamma_k \hat{M}_k \cup \gamma_j \hat{M}_j}
     \]  
   - 监督损失：二值交叉熵（BCE）。

3. **位置感知跨模态交互（Position-aware Cross-Modal Interaction, PCMI）**  
   - 从高斯中心坐标 \(\mu_i\) 通过MLP提取位置嵌入 \(f_{p,i}\)。  
   - 从词特征与高斯引用特征的关联中动态提取文本位置特征 \(f_{p,w,i}\)。  
   - 通过位置引导的注意力机制更新引用特征：  
     \[
     f'_{r,i} = f_{r,i} + \text{softmax}\left(\frac{(f_{r,i}+f_{p,i})(f_w+f_{p,w,i})^T}{\sqrt{D}}\right) f_w
     \]  
   - 更新后的特征 \(f'_{r,i}\) 替代原 \(f_{r,i}\) 计算相似度。

4. **高斯-文本对比学习（Gaussian-Text Contrastive Learning, GTCL）**  
   - 针对语义相似但目标不同的描述，选取与文本相似度最高的前 \(\tau\) 百分比高斯点的引用特征平均值作为正样本高斯嵌入 \(f_g\)。  
   - 对象级对比损失：  
     \[
     L_{con} = -\frac{1}{|P|}\sum_{f_e^+ \in P} \log \frac{\exp(f_g \cdot f_e^+)}{\sum_{f_e' \in P,N} \exp(f_g \cdot f_e')}
     \]  
   - 总损失：\(L_{loss} = L_{bce} + \lambda L_{con}\)。

5. **两阶段优化**  
   - 第一阶段训练ReferSplat生成掩码；第二阶段用第一阶段生成的掩码作为伪标签再训练，进一步细化。

## 3. 实验设计：使用的数据集、基准测试、对比方法

- **数据集**  
  - **Ref-LERF**：基于LERF-OVS扩展，包含4个真实场景（ramen, figurines, teatime, kitchen），共295个自然语言描述（236训练，59测试）。每个对象约5个描述，平均句子长度>13.6 words，强调空间关系和细粒度属性。  
  - **LERF-OVS**：开放词汇3D分割基准（4个场景）。  
  - **3D-OVS**：开放词汇3D分割基准（5个场景：bed, bench, room, sofa, lawn）。

- **基准测试（Benchmark）**  
  - R3DGS任务：平均IoU（mIoU）在Ref-LERF的新颖视图上评估。  
  - 开放词汇分割：mIoU在LERF-OVS和3D-OVS上评估。

- **对比方法**  
  - 2D方法：Grounded SAM（在训练视图生成伪掩码，测试时直接应用于单一视图）。  
  - 3D方法：LangSplat、SPIn-NeRF、GS-Grouping、GOI（均为开放词汇或指代分割的适配版本）。  
  - 消融基线：余弦相似度、乘法基线（文中提出的3D引用场不加PCMI/GTCL）。

## 4. 资源与算力

- **GPU型号**：NVIDIA RTX A6000（单卡）。  
- **训练时长**：在ramen场景上约**58分钟**（整体训练包括RGB表示预训练和引用特征优化）。  
- **存储成本**：每个场景约 **3.3 MB**（引用特征存储）。  
- **训练帧率**：26.8 FPS（推理速度）。  
- 论文未说明多卡训练或大规模集群使用情况，推测为单卡实验。

## 5. 实验数量与充分性

- **实验组数**：  
  - 主任务R3DGS在Ref-LERF上4个场景的定量结果（Tab.8）。  
  - 开放词汇分割：LERF-OVS（4场景，Tab.9）和3D-OVS（5场景，Tab.10）。  
  - 消融实验：  
    - 组件有效性：基线 vs PCMI vs GTCL vs 完整ReferSplat vs 两阶段（Tab.1，2场景）。  
    - 基线配置对比：LangSplat、SPIn-NeRF、余弦相似度、乘法（Tab.2，2场景）。  
    - 伪掩码生成策略对比：Top-1、SAM2、IoU无置信度、IoU有置信度（Tab.3，2场景）。  
    - 跨模态交互设计：去除位置特征、不同组合（Tab.4，2场景）。  
    - 计算开销对比（Tab.5，1场景）。  
    - 语言编码器选择：CLIP vs BERT（Tab.6，4场景平均）。  
    - 引用特征维度：1,4,16,32（Tab.7，2场景）。  
  - 定性可视化（Fig.5，4个场景各一个例子）。  

- **充分性评价**：  
  - **充分**：覆盖了多个场景、多种设置、多类消融，同时验证了在R3DGS和开放词汇两个任务上的有效性。  
  - **客观公平**：与多种现有方法（2D和3D）在同一数据集和指标下比较；消融实验展示了每个模块的边际贡献；开源代码和dataset有助于复现。  
  - **小缺陷**：数据集规模较小（4个场景），虽然足以证明方法有效性，但泛化能力有待更大规模验证。

## 6. 论文的主要结论与发现

- ReferSplat在R3DGS任务上以**mIoU 29.2%**显著优于所有对比方法（第二名GOI为20.5%），得益于3D高斯引用场和位置感知交互。  
- 在开放词汇分割任务上，ReferSplat在LERF-OVS上平均mIoU **55.4%**，在3D-OVS上 **94.1%**，均达到SOTA。  
- 伪掩码生成采用置信度加权IoU策略后，伪掩码质量接近50% mIoU（与人工GT对比），优于top-1或纯IoU选择。  
- PCMI和GTCL两个关键组件各自带来约4-5%的提升，两阶段优化再提升约1-2%。  
- BERT作为语言编码器优于CLIP，因为CLIP更侧重名词类别，而指代表达需要空间和属性理解。  
- 最佳引用特征维度为16，过大或过小均降低性能。

## 7. 优点：方法或实验设计上的亮点

- **任务创新**：首次定义R3DGS问题，构建专用数据集Ref-LERF，促进3D场景语言理解研究。  
- **方法亮点**：  
  - **3D高斯引用场**直接在3D点位置与文本交互，比现有在2D渲染特征上匹配的方法更利于空间推理和遮挡物体识别。  
  - **位置感知跨模态交互**巧妙地将高斯位置信息注入注意力机制，让模型理解“左边”、“靠近”等空间关系。  
  - **高斯-文本对比学习**通过正负样本拉近拉远，解决语义相似但目标不同的歧义。  
  - **伪掩码生成**的置信度加权IoU策略简单有效，提升了训练标签质量。  
- **实验设计**：消融全面，计算成本低（58分钟训练，3.3MB存储），实际部署友好。  
- **开源**：代码、数据集、模型均公开，可复现。

## 8. 不足与局限

- **未考虑动态因素**：当前方法仅处理静态场景，无法应对动态变化（如移动物体）。作者建议未来结合4D Gaussian Splatting（4DGS）。  
- **缺乏3D视觉定位**：任务仅限于分割，未扩展到物体尺寸估计或3D边界框定位，限制了在空间推理和机器人操作中的应用。  
- **数据集规模小**：仅4个室内场景，语言描述总数不足300，多样性有限。模型泛化性到其他场景（如室外、大规模）未验证。作者承认未来需构建大规模数据集。  
- **对遮挡的鲁棒性**：虽然利用了3D多视图知识，但极端遮挡或半透明物体（如玻璃）可能仍然困难，未测试。  
- **对比方法局限**：部分对比方法（如Grounded SAM）是2D方法，在R3DGS任务上天然劣势，但论文未详细讨论公平性（如是否提供多视图训练）。  
- **潜在偏差**：Ref-LERF数据集的物体和描述由作者手工标注，可能引入标注者主观偏差；场景均来自Polycam iPhone采集，图像质量较高，与真实复杂环境有差距。

（完）
