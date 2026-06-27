---
title: "DS-VLM: Diffusion Supervision Vision Language Model"
title_zh: DS-VLM：扩散监督视觉语言模型
authors: "Zhen Sun, Yunhang Shen, Jie Li, Xing Sun, Pingyang Dai, Liujuan Cao, Rongrong Ji"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NEBa0bs5LR"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 扩散监督用于视觉语言模型对齐
tldr: 针对视觉语言模型监督退化和语义稀疏问题，提出DS-VLM框架。通过扩散模型重建输入图像提供直接像素级监督，建立从像素空间到视觉特征的短路径梯度传播。在保留高层语义对齐的同时增强视觉表示，多个VLM基准上取得提升。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 770, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1328, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 546, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 803, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 801, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 802, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1764, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1222, \"height\": 192, \"label\": \"Table\"}]"
motivation: 视觉语言模型存在监督退化与语义稀疏问题。
method: 提出扩散监督机制，通过扩散模型重建输入图像来提供直接的像素级监督。
result: 在多个VLM基准上提升了视觉表示质量和语言对齐。
conclusion: 扩散监督能有效增强VLM的视觉表示学习。
---

## Abstract
Vision-Language Models (VLMs) face two critical limitations in visual representation learning: degraded supervision due to information loss during gradient propagation, and the inherent semantic sparsity of textual supervision compared to visual data. We propose the Diffusion Supervision Vision-Language Model (DS-VLM), a plug-and-play framework that introduces diffusion-based direct supervision for vision-language alignment. By reconstructing input images through a diffusion model conditioned on outputs of the visual encoder and the connector, our method establishes a short-path gradient propagation channel from pixel space to visual features. This approach simultaneously preserves high-level semantic alignment through conventional text supervision while enhancing visual feature quality via pixel-level reconstruction constraints. Extensive experiments conducted across various visual encoders and LLMs of different scales demonstrate the effectiveness of our approach.

---

## 论文详细总结（自动生成）

# DS-VLM：扩散监督视觉语言模型 — 详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前的视觉语言模型（VLM）主要有两个局限：
  - **监督退化**：训练时，视觉编码器和连接器的优化依赖文本监督信号经大语言模型（LLM）反向传播，路径过长导致梯度信息大量损失，参数更新效率低。
  - **语义稀疏性**：文本监督相比图像本身信息量有限（“一图胜千言”），难以完整捕捉图像的细节、结构和语义。

- **研究动机**：探索一种更直接的监督方式，利用图像自身丰富信息来优化视觉编码器和连接器，同时缩短梯度传播路径，从而提升视觉表示质量和多模态对齐效果。

- **整体含义**：提出一个即插即用的框架 DS-VLM，通过在训练阶段引入扩散模型重建输入图像，为视觉特征提供像素级直接监督，在不增加推理开销的前提下显著提升 VLM 在下游任务上的性能。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 将视觉编码器输出（包括低、中、高层特征）和连接器输出特征分别作为**图像模态**和**文本模态**的监督特征，输入一个**多适配器扩散模型**，用于重建原始图像。
- 通过重建损失反向传播，使视觉特征携带更多像素级和语义级信息，同时跳过 LLM 实现**短路径梯度传播**。
- 训练时扩散模型参与，推理时丢弃该模块，不增加参数和计算量。

### 关键技术细节
1. **监督特征选择**：
   - **图像监督**：提取视觉编码器第 8、16、24 层特征（分别对应低、中、高语义级别）。
   - **文本监督**：连接器输出特征（已将图像特征映射到文本嵌入空间）。

2. **多适配器扩散模型（Multi-Adapter Diffusion）**：
   - 基于 Stable Diffusion（SD）UNet 架构，为每种监督特征设计独立的线性适配器（Adapter），并通过 **MOE Cross Attention** 机制将多模态条件注入扩散模型。
   - **MOE Cross Attention**：文本特征和三层图像特征各自拥有独立的交叉注意力层（共享查询 Q），输出通过可学习的路由权重加权求和：
     \[
     P = \text{Softmax}(\text{Pooling}(Q \cdot W_r)), \quad Z_{\text{new}} = P_0 Z' + \sum_{i=1}^3 P_i Z''_i
     \]
     其中 \(W_r \in \mathbb{R}^{d \times 4}\) 为可学习参数，\(P_0\) 为文本注意力权重，\(P_{1-3}\) 为各层图像注意力权重。

3. **训练目标**：
   - 除原始的 VLM 语言生成损失（预测下一个 token）外，额外添加**重建损失**：
     - 对比了像素级 MAE、结构级 SSIM、语义级感知损失（PL），最终选择感知损失（PL）效果最佳。
   - 总损失 = 标准 VLM 损失 + 重建损失，联合优化视觉编码器、连接器和扩散适配器。

4. **推理阶段**：移除扩散模型及适配器，仅保留原始 VLM 架构，零额外开销。

## 3. 实验设计

### 数据集
- **预训练**：558K 图像-描述对（来自 LLaVA-1.5）。
- **指令微调**：665K 对话数据（来自 LLaVA-1.5）。
- 扩展实验：使用 Mini-Gemini 的 1.2M 预训练 + 1.5M 指令数据。

### 评估基准（Benchmark）
| 基准名称 | 考察能力 |
|---------|----------|
| MMBench (MMB) | 综合多模态理解与布局推理 |
| MMStar (MMS) | 细粒度多模态对齐与指令遵循 |
| MMMU | 多学科复杂视觉推理（医学、工程等） |
| MathVista (MV) | 数学推理 |
| OCRBench (OCRB) | 光学字符识别 |
| AI2D | 科学图表理解 |
| HallusionBench (HB) | 幻觉鲁棒性 |
| LLaVABench (LB) | 知识接地与复杂场景理解 |
| ScienceQA (SQA) | 科学问答 |
| MME | 综合多模态评估 |

### 对比方法
- **基线**：LLaVA-1.5（Vicuna-7B/13B，CLIP-L）。
- **扩展对比**：替换视觉编码器为 SigLIP-SO，替换 LLM 为 Llama3-8B、Qwen2-7B。
- **SoTA 对比**：MiniGPT4、Qwen-VL、VisualGLM、PandaGPT、mPLUG-Owl2、Emu2-chat、Yi-VL、ShareGPT-4V。
- **消融实验**：监督特征类型、重建损失类型、交叉注意力机制（共享 vs 独立）、适配器结构（线性 vs Q-Former）。

## 4. 资源与算力

- **论文未明确说明**使用的 GPU 型号、数量及训练时长。
- 仅提及训练配置：
  - 预训练学习率 1e-3，指令微调学习率 2e-5。
  - 批量大小：预训练 256，指令微调 128。
  - LoRA 秩统一设置为 8。
  - 扩散模型迭代步数 50。
- 由于缺乏具体硬件信息，无法评估训练成本。但整体框架设计轻量，推理时扩散模型被移除，因此推理成本与基线相同。

## 5. 实验数量与充分性

### 实验组数
| 实验类型 | 数量（组） |
|---------|-----------|
| 基线对比（不同 VE/LLM/数据量） | 8 组（表 1） |
| SoTA 对比 | 1 组（表 2，含 9 种方法） |
| 监督特征消融 | 5 组（表 3） |
| 重建损失消融 | 3 组（表 4） |
| 交叉注意力机制消融 | 2 组（表 5） |
| 适配器结构消融 | 2 组（表 6） |
| 附录实验（可训练编码器对比、重建损失验证） | 2 组（表 7、表 8） |
| **合计核心实验** | **约 23 组** |

### 充分性与公平性
- **覆盖面广**：涵盖不同视觉编码器（CLIP-L、SigLIP-SO）、不同 LLM（Vicuna 7/13B、Llama3-8B、Qwen2-7B）以及不同数据规模，验证了方法的通用性。
- **公平控制**：严格遵守 LLaVA-1.5 原始训练设置（学习率、批量大小、数据等），保证与基线公平对比。
- **消融全面**：逐一验证各组件贡献（多级监督、损失函数、注意力机制、适配器设计），结论可信。
- **不足**：
  - 缺乏在更大规模 LLM（如 33B、70B）或更复杂任务（如视频理解、多轮对话）上的验证。
  - 未讨论训练稳定性与收敛性分析。
  - 未提供统计显著性检验。

## 6. 论文的主要结论与发现

1. **DS-VLM 显著提升基线性能**：在 Vicuna-7B 设置下，平均提升约 1.4%，在 MMBench、MMMU、LLaVABench 上分别 +2.4%、+2.1%、+2.5%。
2. **通用性强**：替换视觉编码器或 LLM 后仍保持优势，验证了即插即用特性。
3. **多层级监督互补性**：同时使用文本监督和低/中/高层图像监督效果最优，单层或部分层监督性能递减。
4. **感知损失为最佳选择**：相比像素级 MAE 和结构级 SSIM，感知损失能更好地保留语义信息。
5. **独立交叉注意力优于共享**：分离文本和图像注意力可避免模态干扰，提升多模态对齐。
6. **线性适配器优于 Q-Former**：结构更简单、参数更少且效果更好。

## 7. 优点

1. **创新性**：首次将扩散模型直接用于 VLM 训练监督，通过像素级重建提供短路径梯度传播，有效解决监督退化和语义稀疏问题。
2. **实用性**：即插即用，推理时零额外参数和计算，易于集成到现有 VLM 框架。
3. **全面性**：多层级监督及 MOE 交叉注意力设计，充分挖掘视觉特征中的结构化和语义信息。
4. **泛化能力**：在多种视觉编码器、LLM 和数据规模下均验证有效，适用性强。
5. **消融严谨**：对每个组件（监督特征、损失函数、注意力机制、适配器）做了独立评估，结论可靠。

## 8. 不足与局限

1. **未提供计算资源与训练成本**：缺少 GPU 型号、数量、训练时间等信息，难以评估方法的实际部署可行性。
2. **实验规模有限**：
   - 仅基于 LLaVA-1.5 框架，未在更复杂架构（如 Flamingo、InstructBLIP）上验证。
   - 未测试更大参数量的 LLM（≥13B 仅有一种设置）。
   - 未涉及视频、3D、跨模态检索等任务。
3. **依赖扩散模型质量**：重建效果受限于预训练扩散模型（SD）的能力，可能引入偏差或失真。
4. **缺乏训练稳定性分析**：联合优化 VLM 损失和重建损失时，未讨论超参数敏感性、收敛速度或过拟合风险。
5. **未进行统计显著性检验**：性能提升幅度较小（部分 ≤1%），缺少置信区间或 p 值，可能受随机因素影响。
6. **推理阶段零开销前提**：仅对训练阶段有益，若需要微调（如 domain adaptation）则仍需扩散模型参与，增加训练成本。

（完）
