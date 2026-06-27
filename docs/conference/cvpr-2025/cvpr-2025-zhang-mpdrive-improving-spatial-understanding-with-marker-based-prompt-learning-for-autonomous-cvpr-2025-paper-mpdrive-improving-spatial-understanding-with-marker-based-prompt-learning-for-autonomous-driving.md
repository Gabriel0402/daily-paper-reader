---
title: "MPDrive: Improving Spatial Understanding with Marker-Based Prompt Learning for Autonomous Driving"
title_zh: MPDrive：通过基于标记的提示学习提升自动驾驶空间理解
authors: "Zhang, Zhiyuan, Li, Xiaofan, Xu, Zhihao, Peng, Wenjie, Zhou, Zijian, Shi, Miaojing, Huang, Shuangping"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhang_MPDrive_Improving_Spatial_Understanding_with_Marker-Based_Prompt_Learning_for_Autonomous_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 6.0
evidence: 基于标记提示的自动驾驶空间理解
tldr: 自动驾驶视觉问答中空间信息常以文本坐标表示，导致语义鸿沟。MPDrive提出基于视觉标记的提示学习，将坐标转化为简洁标记，保留视觉一致性。在AD-VQA基准上显著提升空间理解准确率，为多模态感知提供了新思路。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-mpdrive-improving-spatial-understanding-with-marker-based-prompt-learning-for-autonomous-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 646, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-mpdrive-improving-spatial-understanding-with-marker-based-prompt-learning-for-autonomous-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1607, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhang-mpdrive-improving-spatial-understanding-with-marker-based-prompt-learning-for-autonomous-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1669, \"height\": 1240, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-mpdrive-improving-spatial-understanding-with-marker-based-prompt-learning-for-autonomous-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1641, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-mpdrive-improving-spatial-understanding-with-marker-based-prompt-learning-for-autonomous-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1565, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-mpdrive-improving-spatial-understanding-with-marker-based-prompt-learning-for-autonomous-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1658, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhang-mpdrive-improving-spatial-understanding-with-marker-based-prompt-learning-for-autonomous-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1777, \"height\": 331, \"label\": \"Table\"}]"
motivation: 文本坐标表示导致空间信息语义鸿沟，影响VQA性能。
method: 用视觉标记代替文本坐标，设计标记提示学习框架。
result: 在自动驾驶VQA任务上显著优于基线方法。
conclusion: 视觉标记作为中间表示可弥合坐标与文本的语义差距。
---

## Abstract
Autonomous driving visual question answering (AD-VQA) aims to answer questions related to perception, prediction, and planning based on given driving scene images, heavily relying on the model's spatial understanding capabilities. Prior works typically express spatial information through textual representations of coordinates, resulting in semantic gaps between visual coordinate representations and textual descriptions. This oversight hinders the accurate transmission of spatial information and increases the expressive burden. To address this, we propose a novel Marker-based Prompt learning framework (MPDrive), which represents spatial coordinates by concise visual markers, ensuring linguistic expressive consistency and enhancing the accuracy of both visual perception and spatial expression in AD-VQA. Specifically, we create marker images by employing a detection expert to overlay object regions with numerical labels, converting complex textual coordinate generation into straightforward text-based visual marker predictions. Moreover, we fuse original and marker images as scene-level features and integrate them with detection priors to derive instance-level features. By combining these features, we construct dual-granularity visual prompts that stimulate the LLM's spatial perception capabilities. Extensive experiments on the DriveLM and CODA-LM datasets show that MPDrive achieves state-of-the-art performance, particularly in cases requiring sophisticated spatial understanding.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：自动驾驶视觉问答（AD-VQA）严重依赖模型的空间理解能力，但现有方法通常将物体坐标转化为文本描述（如 `<x, y>`），导致视觉坐标表示与语言描述之间存在 **语义鸿沟**，影响了空间信息的准确传递，也增加了语言表达的负担。
- **整体含义**：为弥合这一鸿沟，论文提出 **MPDrive（Marker-Based Prompt Learning）**，用简洁的 **视觉标记（visual marker）** 替代文本坐标，从而在保持语言表达一致性的同时，显著提升空间感知精度。

---

### 2. 论文提出的方法论：核心思想与关键技术细节
- **核心思想**：将复杂的空间坐标生成问题转化为直观的 **文本索引预测**——在图像上为每个检测到的物体叠加半透明遮罩并标注数字索引，模型只需预测物体对应的索引号，再由检测专家映射为实际坐标。
- **关键技术细节**：
  - **Visual Marker 生成**：使用检测专家（StreamPETR）识别交通要素，生成二值掩码和质心坐标，在原始图像上叠加半透明掩码和索引标签；若问题中引用了新坐标（距已有坐标 > 50 像素），则动态分配新索引。
  - **Marker ControlNet（MCNet）**：冻结原视觉编码器参数，复制一个可训练的控制块（使用 LoRA 低秩适配，rank=16），通过零初始化线性层融合原始图像特征与标记图像特征，实现场景级特征融合，保留原始视觉信息的同时引入标记信息。
  - **Perception-Enhanced Spatial Prompt Learning（PSPL）**：提取 **场景级视觉提示**（MCNet 的输出特征经过 MLP 转换）和 **实例级视觉提示**（对场景层特征进行掩码平均池化），两者拼接后输入 LLM，增强多粒度的空间感知。
  - **训练与推理**：LLM 和 MCNet 中的视觉编码器均使用 LoRA 微调，训练目标为交叉熵损失；推理时 LLM 输出物体索引，再映射为坐标。

---

### 3. 实验设计：数据集、Benchmark 与对比方法
- **数据集**：
  - **DriveLM**：多视角（6 张图像）AD-VQA 数据集，341,353 训练 QA 对，18,817 验证 QA 对。
  - **CODA-LM**：单视角（前视图像）AD-VQA 数据集，20,495 训练 QA 对，193 验证 QA 对。
- **评估指标**：BLEU-4、ROUGE-L、CIDEr、METEOR（语言一致性），以及 Match（预测坐标与真值中心点距离 < 16 像素的比例）和 Accuracy（多选/是非题正确率）。
- **对比方法**：
  - DriveLM 上：DriveLM-Agent（图推理）、EM-VLM4AD、MiniDrive、LLaMA-Adapter、InternVL-2 等。
  - CODA-LM 上：LLaVA1.5、Qwen-VL-Chat、Qwen-VL-Max、MiniDrive 等。

---

### 4. 资源与算力
- 训练硬件：**8 张 A800 GPU**。
- 训练配置：
  - DriveLM：batch size 128，训练 3,000 次迭代（约 1 epoch）。
  - CODA-LM：batch size 128，训练 2,000 次迭代（约 12 epochs）。
- 优化器：AdamW，初始学习率 5e-4，余弦学习率调度，权重衰减 0.01。
- 图像分辨率：448×448，最大检测物体数 100。

---

### 5. 实验数量与充分性
- **实验数量**：总计 **4 张主要表格 + 1 张定性案例图**：
  - 表 1（DriveLM 定量对比）、表 2（CODA-LM 定量对比）、表 3（不同 MLLM 上的消融）、表 4（各组件消融）。
  - 图 3（2 个定性示例，对比 InternVL-2 和 MPDrive）。
- **充分性判断**：
  - 覆盖了 **多视角（DriveLM）** 和 **单视角（CODA-LM）** 场景，以及 **不同基础 MLLM（InternVL-2、LLaMA-Adapter）**，验证了方法的模型无关性。
  - 消融实验逐步拆解 Visual Marker、MCNet、实例级提示的效果，因果清晰。
  - 与多个 SOTA 方法公平对比（采用相同数据划分和评估协议）。
  - **客观性**：所有结果均基于公开数据集和标准指标，消融实验保持其他设置不变，公平合理。

---

### 6. 论文的主要结论与发现
- MPDrive 在 **DriveLM** 上取得 Match 13.43（远超 InternVL-2 的 7.59）、Accuracy 85.18，语言指标 CIDEr 3.56、METEOR 38.31 均为最高。
- 在 **CODA-LM** 上 General Text-Score 41.80（第二高 34.60），Region Perception 各子类均领先，Suggestion 58.20（第二高 47.40）。
- 视觉标记 **有效弥合了坐标与文本的语义差距**，显著提升了空间感知能力，尤其适用于复杂空间关系场景。
- PSPL 中的场景级和实例级双粒度提示均贡献不可替代：实例级提示使 Match 从 9.70 提升至 13.43，且语言指标全面上升。
- MPDrive 可良好适配不同 MLLM（LLaMA-Adapter 和 InternVL-2），具有通用性。

---

### 7. 优点：方法或实验设计上的亮点
- **方法创新**：首次在 AD-VQA 中以 **视觉标记** 替代文本坐标，将坐标生成转化为索引预测，逻辑简洁且与语言模态对齐。
- **模块化设计**：MCNet 在保留原始图像特征的同时引入标记信息，PSPL 融合场景/实例层级，结构清晰、可替换。
- **实验全面**：覆盖多视角/单视角、多种 MLLM、多个消融维度，验证充分。
- **计算高效**：使用 LoRA 微调，训练迭代次数少（DriveLM 仅 1 epoch），在 8 卡 A800 上可行。

---

### 8. 不足与局限
- **依赖检测专家**：MPDrive 的标记生成和坐标映射依赖于 StreamPETR 的输出，该专家的错误会向下游传播，影响整体性能。
- **长时域感知未涉及**：论文指出，尽管 MPDrive 增强了空间感知，但 **长时域时间感知**（如跨帧推理）仍是自动驾驶中的重要挑战，当前方法未覆盖。
- **评估数据集规模有限**：CODA-LM 验证集仅 193 个 QA 对，统计显著性可能受限；DriveLM 验证集也相对较小。
- **鲁棒性验证不足**：未在光照变化、遮挡严重等极端驾驶场景下进行压力测试，也未与基于 3D 或时序的方法（如 Atlas）对比。

（完）
