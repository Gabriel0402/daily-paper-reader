---
title: "When Every Millisecond Counts: Real-Time Anomaly Detection via the Multimodal Asynchronous Hybrid Network"
title_zh: 分秒必争：基于多模态异步混合网络的实时异常检测
authors: "Dong Xiao, Guangyao Chen, Peixi Peng, Yangru Huang, Yifan Zhao, Yongxing Dai, Yonghong Tian"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oYyaVSqEFu"
tags: ["query:mmseg"]
score: 6.0
evidence: 多模态异步融合用于自动驾驶实时异常检测
tldr: 针对自动驾驶中异常检测忽略响应时间的问题，提出多模态异步混合网络。将事件相机的高时间分辨率与RGB图像的空间特征结合，通过异步图神经网络和CNN进行时空融合，在时间敏感场景下实现低延迟高精度检测。实验表明该方法在速度和准确度上均优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 1033, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1770, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1732, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1744, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1730, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1763, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1771, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1415, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1249, \"height\": 1047, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1774, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1709, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1359, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1321, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1097, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1309, \"height\": 202, \"label\": \"Table\"}]"
motivation: 现有自动驾驶异常检测方法忽略响应时间，难以满足实时需求。
method: 提出多模态异步混合网络，结合事件相机流和RGB图像，使用异步GNN和CNN提取时空特征。
result: 在时间敏感场景下实现了低延迟高精度的异常检测。
conclusion: 多模态异步融合对自动驾驶实时感知至关重要。
---

## Abstract
Anomaly detection is essential for the safety and reliability of autonomous driving systems. Current methods often focus on detection accuracy but neglect response time, which is critical in time-sensitive driving scenarios. In this paper, we introduce real-time anomaly detection for autonomous driving, prioritizing both minimal response time and high accuracy. We propose a novel multimodal asynchronous hybrid network that combines event streams from event cameras with image data from RGB cameras. Our network utilizes the high temporal resolution of event cameras through an asynchronous Graph Neural Network and integrates it with spatial features extracted by a CNN from RGB images. This combination effectively captures both the temporal dynamics and spatial details of the driving environment, enabling swift and precise anomaly detection. Extensive experiments on benchmark datasets show that our approach outperforms existing methods in both accuracy and response time, achieving millisecond-level real-time performance.

---

## 论文详细总结（自动生成）

# 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：现有自动驾驶异常检测方法过度关注检测准确率，却忽略了实际应用中至关重要的 **响应时间**（response time）。在时间敏感的驾驶场景（如行人突然横穿、车辆紧急切入）中，毫秒级的延迟可能直接决定安全制动与碰撞的差异。
- **核心问题**：如何在保证高检测精度的同时，将 **推理延迟** 和 **检测延迟**（从异常发生到检测到的时间）降至最低，实现毫秒级实时异常检测。
- **背景贡献**：首次将 **事件相机**（event camera）的高时间分辨率特性引入交通事故异常检测领域，并正式提出 **实时异常检测**（Real-Time Anomaly Detection）任务，将响应时间作为关键评价指标。

# 2. 方法论
## 2.1 核心思想
- 利用事件相机（微秒级亮度变化响应，天生稀疏异步）与 RGB 相机（丰富空间信息但高延迟）的 **互补优势**，设计 **多模态异步混合网络**，在极低延迟下融合时空特征，实现快速准确的异常判定。
- 异步设计：事件流通过 **异步图神经网络（Asynchronous GNN）** 处理，保留原始事件的时序粒度；RGB 图像通过 **CNN（ResNet）** 提取外观特征；两者通过 **单向特征共享** 融合（CNN 特征增强 GNN 节点特征，但不反向影响 CNN）。

## 2.2 关键技术细节
- **事件图构建**：事件流中的每个事件（像素坐标、时间戳、极性）作为图节点，基于空间和时间邻近度（半径 R）建边，每个节点最多连接 16 个邻居。边特征 \(e_{ij} = \frac{1}{2}(n_{j,xy} - n_{i,xy}) + \frac{1}{2}\)。
- **异步 GNN（DAGr）**：使用残差图卷积层 + 样条卷积（spline convolution），公式：  
  \(f_i' = W_c f_i + \sum_{j\in\mathcal{N}(i)} W(e_{ij}) f_j\)。样条卷积通过查找表加速推理，保持时序一致性（方向体素池化）。
- **特征融合**：拼接每个节点位置处的 CNN 特征 \(g_I(\hat{x}_i)\) 与 GNN 节点特征 \(f_i\)：\(f_i' = [f_i, g_I(\hat{x}_i)]\)。
- **目标级特征提取**：检测器（YOLOX）输出边界框后，提取框内事件特征 \(o_{t,i}\)（通过 GNN）与 RGB 特征 \(g_{t,i}\)，拼接降维得到 \(f_{t,i}\)。
- **时空关系学习**：分别对边界框特征 \(b_{t,i}\) 和融合特征 \(f_{t,i}\) 使用两个 **GRU** 捕捉时序依赖：
  \[
  h_{b,t,i} = \text{GRU}(b_{t,i}, h_{b,t-1,i};\theta_1),\quad h_{f,t,i} = \text{GRU}(f_{t,i}, h_{f,t-1,i};\theta_2).
  \]
- **注意力机制**：对 GRU 隐藏状态进行自注意力加权，突出异常对象：
  \[
  \hat{H}_{b,t} = H_{b,t}\,\text{softmax}\left(\tanh(H_{b,t}^\top w_b)\right),\quad \hat{H}_{f,t} \text{同理}.
  \]
- **风险分数预测**：拼接注意力加权特征后，经全连接层和 softmax 得到每个对象的异常分数 \(s_{t,i}\)。
- **响应时间定义**：\(R = \Delta T_{\text{detection}} + T_{\text{inference}}\)，其中 \(\Delta T_{\text{detection}}\) 为检测延迟，\(T_{\text{inference}}\) 为模型推理时间。

# 3. 实验设计
## 3.1 数据集
- **主要数据集**：**ROL**（Karim et al., 2023）和 **DoTA**（Yao et al., 2022），两者均包含详细时间、空间、类别标注。由于现有真实数据集缺少事件模态，使用 **v2e** 转换工具从 RGB 视频生成合成事件流。
- **自建 Rush-Out 数据集**：从 ROL 和 DoTA 中挑选“突然出现物体”的危险场景，共 1084 段视频（20fps, 1280×720），专门评估低延迟能力。
- **验证数据集**：DSEC（真实事件数据）用于验证 v2e 合成数据的有效性。

## 3.2 Benchmark 与对比方法
- **对比方法**（共 12 种）：ConvAE, ConvLSTMAE, AnoPred, FOL（四种变体：IoU, Mask, STD, Ensemble）, MAMTCF, AM-Net, STFE, TTHF。
- **额外实时方法对比**：AED-MAE, EfficientAD, MOVAD（帧级实时检测方法）。
- **评价指标**：AUC, AP, AUC-Frame, mTTA（平均预警提前时间），**mResponse**（多阈值平均检测延迟，本文新提）, FPS。

# 4. 资源与算力
- **未明确训练用 GPU 型号与数量**：论文仅在附录中说明训练参数（RGB：30 epochs，batch size 64，每 epoch 1920 图像，共 57600 次数据传递；事件组件：batch size 32，150000 iterations，约 2500 epochs），使用 Adam（学习率 0.001）和 AdamW（学习率 2×10⁻⁴）优化器，ReduceLROnPlateau 调度器。
- **运行资源**：推理时每个事件需 8.732 MFLOPs，占用 23.5 GB 显存。典型场景下（平均 560k 事件/秒）计算量约 4.89 TFLOPs；极端场景（10M 事件/秒）计算量约 87.32 TFLOPs，可在 Orin/Atlan/Thor 等芯片上部署，但 Xavier/Parker 在极端场景下可能不足。
- **硬件同步约束**：双摄像头（RGB+事件）同步误差仅 78 微秒，事件相机本身约 6ms 延迟，满足实时要求。

# 5. 实验数量与充分性
- **实验组数**：主表（表1）在 ROL 和 DoTA 上对比 12 种方法；消融实验（表2、附录表5）共至少 9 种配置；网络深度影响（表3）；不同 backbone（表4）；两阶段架构对比（附录表6）；Rush-Out 数据集对比（附录表7）；实时方法对比（附录表8）；DSEC 验证（附录表9）；极端场景对比（附录表11）。
- **客观性与公平性**：对比充分，涵盖了经典重构法、预测法、特征融合法、最新文本融合法等；消融实验验证了各模块（RGB、Event、GRU、Attention、BBox、Object 等）的必要性；在自建数据集和极端场景下也验证了鲁棒性。
- **潜在偏差**：事件数据使用合成 v2e，而非真实事件相机采集，可能无法完全反映现实噪声和异步特性；但论文通过 DSEC 验证表明 v2e 对检测性能影响很小。

# 6. 主要结论与发现
- 提出方法在 **准确率**（AUC、AP）和 **响应时间**（mResponse、mTTA、FPS）上全面优于所有对比方法，实现毫秒级实时性能（579 FPS，mResponse 约 1.17s）。
- **事件流**极大地提升了异常检测的 **早期预警能力**（mTTA 提升至 2.80s），尤其在快速移动物体突然出现的场景中，能实现 **帧间检测**（inter-frame anomaly detection），即在物体未完整出现前即发出警报。
- 模态融合中，**RGB 提供空间细节提升检测精度**，**事件流提供运动时序信息加速检测**，两者互补；**GRU 负责时间累积，Attention 突出异常对象**。
- 在极端光照（强背光、低光照）下，事件相机优势显著，所提方法大幅领先其他方法。

# 7. 优点
- **首次将事件流用于自动驾驶异常检测**：充分利用事件相机的高时间分辨率和异步性质，突破了传统帧级方法的延迟瓶颈。
- **端到端异步混合架构**：CNN + 异步 GNN 设计兼顾空间和时序细节，单向特征共享避免冗余，推理速度快（579 FPS）。
- **模块化设计**：可扩展网络深度和 backbone（如 ViT），仅带来微小延迟增加，便于适应不同精度/速度需求。
- **新指标 mResponse**：多阈值平均检测延迟，更全面反映实时性能。
- **丰富的消融与敏感性分析**：验证了每个组件的贡献，并分析了 IOU 阈值、置信度阈值的敏感度，增强了可信度。
- **顾及实际部署**：讨论了在主流自动驾驶芯片上的计算开销和同步问题。

# 8. 不足与局限
- **依赖对象检测器准确率**：附录 E 明确指出，在模糊或小目标场景下检测器失败会导致异常检测失效，且无法恢复缺失的时序特征，这是当前系统的主要瓶颈。
- **事件数据为合成生成**：使用 v2e 转换为事件流，而非真实事件相机采集，虽然通过 DSEC 验证了有效性，但真实场景中的传感器噪声、运动模糊等可能仍有差异。
- **计算负载约束**：在高速极端场景（10M 事件/秒）下计算量高达 87.32 TFLOPs，低端芯片（Xavier/Parker）可能无法胜任，需要量化等优化。
- **训练细节透明度不足**：未明确训练用的 GPU 型号、数量和总时间，复现时需自行估算。
- **场景覆盖有限**：虽然新增了 Rush-Out 数据集，但整体实验仍基于有限公开数据集，真实世界多样化（如夜间、雨雾）的异常类型可能未充分覆盖。
- **未考虑多异常同时出现**：当前方法基于单对象分数，复杂度场景下可能注意力分配不当。

（完）
