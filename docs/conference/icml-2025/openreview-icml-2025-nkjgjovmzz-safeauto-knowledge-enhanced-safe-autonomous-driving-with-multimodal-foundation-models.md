---
title: "SafeAuto: Knowledge-Enhanced Safe Autonomous Driving with Multimodal Foundation Models"
title_zh: "SafeAuto: 知识增强的多模态基础模型安全自动驾驶"
authors: "Jiawei Zhang, Xuan Yang, Taiqi Wang, Yu Yao, Aleksandr Petiushko, Bo Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=nKJGjovmZz"
tags: ["query:mmseg"]
score: 7.0
evidence: 多模态基础模型用于安全自动驾驶，结合知识增强
tldr: 传统自动驾驶在高层次推理与低层控制间存在鸿沟。SafeAuto利用多模态大语言模型（MLLM）统一感知与推理，并通过位置相关交叉熵损失融入安全知识。实验表明该方法能有效提升控制信号预测的准确性和安全性，为基于MLLM的自动驾驶提供了实用方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1741, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 750, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1053, \"height\": 1051, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1747, \"height\": 810, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1753, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1748, \"height\": 963, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nkjgjovmzz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1719, \"height\": 1152, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 741, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 736, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1769, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 976, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 896, \"height\": 671, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1771, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nkjgjovmzz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 627, \"height\": 286, \"label\": \"Table\"}]"
motivation: 自动驾驶系统缺乏高层次推理与安全知识融合。
method: 使用MLLM处理视觉和文本，提出PDCE损失加强控制信号学习。
result: 在自动驾驶模拟中控制精度和安全性提升。
conclusion: 知识增强的MLLM能有效改善自动驾驶决策。
---

## Abstract
Traditional autonomous driving systems often struggle to connect high-level reasoning with low-level control, leading to suboptimal and sometimes unsafe behaviors. Recent advances in multimodal large language models (MLLMs), which process both visual and textual data, offer an opportunity to unify perception and reasoning. However, effectively embedding precise safety knowledge into MLLMs for autonomous driving remains a significant challenge.
To address this, we propose SafeAuto, a framework that enhances MLLM-based autonomous driving by incorporating both unstructured and structured knowledge. First, we introduce a Position-Dependent Cross-Entropy (PDCE) loss to improve low-level control signal predictions when values are represented as text. Second, to explicitly integrate safety knowledge, we develop a reasoning component that translates traffic rules into first-order logic (e.g., "red light => stop") and embeds them into a probabilistic graphical model (e.g., Markov Logic Network) to verify predicted actions using recognized environmental attributes.
Additionally, our Multimodal Retrieval-Augmented Generation (RAG) model leverages video, control signals, and environmental attributes to learn from past driving experiences. Integrating PDCE, MLN, and Multimodal RAG, SafeAuto outperforms existing baselines across multiple datasets, enabling more accurate, reliable, and safer autonomous driving. The code is available at https://github.com/AI-secure/SafeAuto.

---

## 论文详细总结（自动生成）

# SafeAuto: 知识增强的多模态基础模型安全自动驾驶 — 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：传统自动驾驶（AD）系统通常将高层次推理（如“应该减速停车”）与低层控制信号（如具体速度/转向角）分离为独立模块，导致两者关联性弱、行为不连贯，且缺乏安全知识保障。
- **背景**：多模态大语言模型（MLLM）能统一处理图像、视频和文本，有潜力桥接高层推理与低层控制。但现有基于MLLM的方法存在两大缺陷：
  - 低层数值预测：作为文本生成训练时，交叉熵（CE）损失不关注数值距离，而回归用的MSE损失会破坏自回归语言能力；用线性层解码则丢失问答能力。
  - 高层动作预测：纯数据驱动，缺乏对交通规则等结构化知识的显式利用，容易产生不安全/违法动作；即使将规则嵌入上下文，仍存在幻觉问题。
- **目标**：提出**SafeAuto**框架，通过三种创新模块同时提升低层数值精度和高层安全合规性，实现更准确、可靠、安全的自动驾驶。

## 2. 方法论：核心思想、关键技术与算法流程

**总体框架**：基于Video-LLaVA + Vicuna 1.5 7B，输入视频帧和历史控制信号文本，输出高层动作描述、高层理由和低层控制信号（速度/曲率等）。训练时使用PDCE损失并加入RAG检索；推理时先由MLLM生成高层动作，再经MLN后安全验证，必要时覆盖并重新生成。

### 2.1 位置相关交叉熵损失（PDCE Loss）

- **动机**：标准CE损失对各数字位统一对待，导致预测值距离真实值近时不一定有更低损失（见图2(a)出现双峰）。
- **原理**：将CE损失改造得像MSE，同时保持自回归文本输出。
  - **Digit-Level Loss Adjustment**：用以目标数字为中心的高斯分布 \( G(\mu,\sigma) \) 替代独热标签，计算KL散度，使数字相近的预测损失更低。
  - **Place-Level Weighting**：每位权重 \( w_i = \prod_{j=1}^{i} D(\mu_j,\sigma)[\mu_j] \)，即前几位目标概率的乘积，高位误差受更大惩罚。
- **最终形式**：  
  \[
  \text{PDCE loss} = \sum_{i=1}^{n} w_i \cdot \text{KL}(P_i \| D(\mu_i, \sigma))
  \]
  其中 \( n \) 为表示数字的位数（固定长度，如“08.100”），\( P_i \) 为MLLM在该位的预测分布。
- **训练技巧**：\( \sigma \) 从0.01几何增长到0.35，稳定训练。

### 2.2 知识增强的后安全验证（Markov Logic Network, MLN）

- **将交通规则（来自加州驾驶员手册）转化为一阶逻辑公式**，每个公式附权重（学习得到）。
- **谓词类型**：
  - **未观察谓词**：主动作（Accelerate, Stop, TurnLeft等），需推理。
  - **观察谓词**：
    - MLLM动作谓词（如MLLMAccelerate），从高层描述提取。
    - 环境谓词（如SolidRedLight, StopSign），通过YOLOv8检测器+历史控制信号GPT-4o提取。
    - 历史控制信号谓词（如HCSKeep）。
- **推理**：最大化条件概率 \( P(U|O) \)，寻找最可能的动作集合（有限可能世界）。若MLN输出动作与MLLM矛盾，则覆盖MLLM高层回答并重新询问。
- **训练**：使用真实+模拟数据，学习公式权重，正则化避免过拟合。

### 2.3 多模态检索增强生成（Multimodal RAG）

- **目标**：构建统一嵌入，检索相似驾驶经验，用于上下文增强。
- **模态**：
  - 视频嵌入 \( Z_v \)：LanguageBind编码→全局平均池化得1024维。
  - 控制信号向量 \( Z_c \)：28维（4种信号×7历史值）。
  - 环境谓词向量 \( Z_p \)：M维二进制向量（M为环境谓词总数）。
- **统一嵌入构建**：各模态经独立投影器映射，加权求和后经投影器得 \( Z_u \)。
  - 权重：\( w_v=0.4, w_c=0.4, w_p=0.2 \)。
- **训练损失**：以文本描述（如“The car is slowing to a stop for the red light”）的嵌入 \( Z_t \) 为监督，使 \( Z_u \) 的相似矩阵与 \( Z_t \) 的相似矩阵（经温度缩放）接近（KL散度最小化）。训练时批次采样，计算相似度矩阵并优化。
- **检索**：训练后对每个测试用例，从训练库中检索Top K最相似样本，将其上下文（视频+控制信号）拼入MLLM输入。

## 3. 实验设计

### 3.1 数据集与场景

| 数据集 | 内容 | 任务 | 规模 |
|--------|------|------|------|
| **BDD-X** | 行车视频、历史控制信号、高层动作描述/理由、低层控制信号 | ①高层动作问答；②高层理由问答；③低层速度/方向预测 | 训练16,390条对话，测试2,123条 |
| **DriveLM**（基于nuScenes） | 当前帧6视角图、历史轨迹、规划/行为多项选择、未来轨迹 | ①规划安全动作（多项选择）；②行为（速度/转向）；③低层运动（3秒轨迹） | 训练3,447条，测试685条 |

### 3.2 对比方法

- **BDD-X**：ADAPT（视频Transformer双分支）、TimeLLM（LLM时间序列）、DriveGPT4（首个MLLM端到端）、RAGDriver（基于三元组损失检索）。
- **DriveLM**：UniAD（Full/Single）、BLIP-RT-2（RT-2方式）、DriveLM-Agent（图VQA+运动token化）。

### 3.3 评价指标

- **高层**：BLEU-4、CIDEr、METEOR；额外动作谓词准确率（通过GPT-4o转换）。
- **低层**：BDD-X：RMSE（速度/方向）和容忍准确率 Aδ；DriveLM：行为准确率（速度/转向），运动平均位移误差 ADE。

## 4. 资源与算力

- **GPU**：8× NVIDIA A6000。
- **训练细节**：
  - BDD-X：2 epochs，batch size 128。
  - DriveLM：4 epochs，batch size 64。
  - 学习率：\( 5\times10^{-2} \)。
  - MLN：300 epochs，学习率 \( 1\times10^{-5} \)。
  - 多模态RAG投影器：100 epochs，batch size 2048（BDD-X）/512（DriveLM），学习率0.001。
- 明确说明了计算资源，但未提及总的训练时间/GPU小时。

## 5. 实验数量与充分性

- **主要实验**：两个数据集上对比多个基线，报告全部指标（高层+低层）。
- **消融实验**：
  - 各模块贡献：Base / PDCE / PDCE+MLN / PDCE+RAG / 完整（表4、5、13）。
  - PDCE损失中 σ 变化对RMSE的影响（图3）。
  - 环境谓词（EP）对RAG的影响（有/无 EP，不同K值）（表6）。
  - 谓词选择：MLLM动作谓词+Top K环境谓词（表14）。
  - 规则违反率（表15）。
- **案例研究**：高层动作、低层动作、token概率分布、MLN纠正（图5-8）。
- **充分性评估**：
  - 覆盖了核心模块独立与组合效果，验证了设计。
  - 超参数（σ、K、谓词数量）的影响均有探讨。
  - 公平性：使用了统一的基础模型（Video-LLaVA），对比基线为公开SOTA，且超参数调优明确。
  - 不足：仅在两个静态数据集上评测，未涉及真实道路测试或闭环仿真。

## 6. 主要结论与发现

1. **PDCE Loss**：使低层数值预测RMSE在BDD-X上速度降低5.8%、方向降低14.1%；且保持高层问答能力不变。
2. **MLN后安全验证**：纠正不安全动作，在BDD-X上规则违反率从11.64%降至4.50%，在DriveLM上从1.03%降至0.75%。
3. **多模态RAG**：大幅提升高层性能——BDD-X动作CIDEr从221.5升至337.4，动作谓词准确率从61.75%升至92.18%；DriveLM行为准确率从60.58%升至74.60%。
4. 整体**SafeAuto**在高层和低层指标上均超越所有对比基线，尤其低层运动预测效果接近纯回归方法UniAD（Full）（ADE 0.84 vs 0.80）。
5. **环境谓词**的加入对RAG检索至关重要（表6），表明二进制显式表示能有效减少原始视频/控制信号中的噪声。

## 7. 优点

- **模块可插拔**：三个组件均可独立使用或组合，易于迁移到其他MLLM自动驾驶框架。
- **PDCE Loss创新**：在不破坏自回归能力的前提下实现类似MSE的数值优化，解决了离散token回归的常见矛盾。
- **显式安全验证**：利用MLN将交通规则形式化并与概率推理结合，提供可解释的后验纠正，不同于单纯将规则写入上下文的做法。
- **RAG设计精巧**：通过文本相似度学习多模态联合嵌入，并利用环境谓词提升鲁棒性；检索效率高（BDD-X仅K=2即可显著提升）。
- **实验充分**：在两个不同特点的数据集上全面评估，消融实验严谨，揭示各组件贡献。

## 8. 不足与局限

- **分布设计局限**：PDCE中使用的Gaussian分布 \( D(\mu,\sigma) \) 并非最优，可能可通过更复杂分布（如binomial或可学习分布）进一步提升。
- **谓词提取质量**：环境谓词依赖YOLOv8检测器（在LISA上微调）和GPT-4o，存在检测错误或提取不完整风险；在复杂场景或夜间可能导致错误谓词，影响MLN和RAG。
- **RAG后处理**：检索后未增加过滤或重排序，低质量检索可能引入噪声；论文提及可作为未来工作。
- **计算开销**：MLLM微调+检索需要较大GPU资源；实时推理时检索+MLN验证可能带来延迟，未讨论系统实际部署可行性。
- **数据集限制**：BDD-X和DriveLM均为离线数据集，未验证在闭环物理仿真或真实道路中的泛化能力；仅包含有限场景（如红绿灯、停止标志等），缺乏更复杂交互。
- **泛化性**：交通规则基于加州手册，不同地区法规差异需重新设计谓词和公式；知识库维护需要人工介入。
- **未评估敏感性与稳健性**：未测试对对抗攻击、传感器故障或罕见场景的鲁棒性。

（完）
