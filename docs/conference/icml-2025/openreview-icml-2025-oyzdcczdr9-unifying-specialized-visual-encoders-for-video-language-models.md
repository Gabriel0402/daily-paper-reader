---
title: Unifying Specialized Visual Encoders for Video Language Models
title_zh: 为视频语言模型统一专用视觉编码器
authors: "Jihoon Chung, Tyler Zhu, Max Gonzalez Saez-Diez, Juan Carlos Niebles, Honglu Zhou, Olga Russakovsky"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oYzDcCZdR9"
tags: ["query:mmseg"]
score: 4.0
evidence: 用于语言模型的多模态视频表示（与分割相关）
tldr: 针对当前视频大语言模型仅使用单一视觉编码器导致视觉信息受限的问题，本文提出MERV多编码器视频表示，通过空时对齐、投影和交叉注意力融合多种编码器特征，实现了更全面的视频理解。在视频问答和视频字幕等任务上，MERV均取得了显著性能提升。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1686, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 772, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 798, \"height\": 822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1681, \"height\": 1586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1752, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1706, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1591, \"height\": 2048, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1687, \"height\": 1377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1702, \"height\": 887, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1782, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 497, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 500, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 510, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1431, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1613, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1260, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 943, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 942, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1603, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1686, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 587, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1690, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1693, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1605, \"height\": 360, \"label\": \"Table\"}]"
motivation: 现有视频语言模型仅使用单一视觉编码器，限制了视觉信息的丰富性。
method: 提出MERV框架，融合多个专用视觉编码器的特征，通过空时对齐和交叉注意力实现高效集成。
result: "在多个视频理解基准上准确率提升高达4.62%。"
conclusion: MERV为视频大语言模型提供了一种有效的多编码器融合策略。
---

## Abstract
Recent advances in vision backbones have yielded powerful and diverse visual and video encoders. Yet, current Video Large Language Models encode visual inputs using an encoder from a single backbone family, limiting the amount and type of visual information they can process. We propose MERV, a Multi-Encoder Video Representation, which utilizes multiple encoders for a comprehensive video representation. To optimize heterogeneous features from a broad spectrum of encoders and ensure efficient and coherent feature integration, MERV first aligns encoder features spatio-temporally, then projects them into a unified structure, and finally fuses them through cross-attention. Under fair comparison, MERV achieves up to 4.62% higher accuracy than its base model, while introducing minimal extra parameters and training faster than equivalent single-encoder methods after parallelizing visual processing. Qualitative analysis shows MERV successfully captures and integrates domain knowledge from each encoder, opening new possibilities for scaling enhanced video understanding.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：当前视频大语言模型（VideoLLMs）通常仅使用单一视觉编码器（如CLIP或LanguageBind）来提取视频特征。不同编码器在预训练数据、目标和架构上存在差异，导致各自具有独特的优势和局限性：例如，对比学习编码器擅长视觉-语言语义对齐，但缺乏细粒度物体理解；视频编码器如ViViT擅长时空建模，但语言理解较弱。单一编码器限制了模型能够处理的视觉信息的类型和丰富度。
- **整体含义**：本文提出MERV（Multi-Encoder Video Representation），旨在通过融合多个专用视觉编码器的特征来获得更全面的视频表示，从而提升VideoLLM在多种视频理解任务上的能力。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：同时使用多个不同类型的视觉编码器（包括空间专家、时间专家、图像-语言对比专家和视频-语言对比专家），通过空时对齐、特征投影和交叉注意力融合，生成统一的视频表示，再输入到LLM中进行语言生成。
- **关键技术细节**：
  1. **多编码器特征提取**：选择四个编码器：
     - DINOv2（空间专家，自监督学习，关注物体局部对应）
     - ViViT（时间专家，基于视频的时空注意力，捕捉长程时间依赖）
     - SigLIP（图像-语言对比专家，对齐图像和文本）
     - LanguageBind（视频-语言对比专家，对齐视频和文本）
  2. **空时对齐**：所有编码器的输入帧数T被调整为使得输出时间维度t相同。采用自适应2D平均池化将不同编码器的空间特征尺寸对齐到统一的h×w。
  3. **预融合投影**：对每个编码器的特征$v_e \in \mathbb{R}^{t \times h_e \times w_e \times d_e}$，先进行2D平均池化（空间压缩到h×w），再通过线性层$W_e \in \mathbb{R}^{d_e \times d}$投影到LLM维度d，得到$x_e \in \mathbb{R}^{\ell \times d}$（$\ell = t \times h \times w$）。
  4. **特征融合**：采用交叉注意力机制。查询Q为可学习的单token（$\mathbb{R}^{1 \times d}$），键为各编码器投影特征在序列维度上平均后的结果$X \in \mathbb{R}^{N \times d}$，值为各编码器原始序列特征$X \in \mathbb{R}^{N \times \ell \times d}$。最终融合特征$O = \text{Softmax}\left(\frac{Q X^\top}{\sqrt{d}}\right) X \in \mathbb{R}^{\ell \times d}$。此过程实现了加性混合。
  5. **LLM生成**：将融合后的视觉嵌入与分词后的文本拼接，输入LLaMA-2 7B模型进行生成。

## 3. 实验设计：使用的数据集/场景、benchmark、对比方法
- **数据集与Benchmark**：
  - **开放问答（Open-ended QA）**：MSVD-QA、MSRVTT-QA、TGIF-QA、ActivityNet-QA。
  - **多项选择（Multiple-choice）**：Perception Test、NExT-QA、VLEP、TVQA。
  - **额外分析**：Something-Something v2（SSv2）上的5-way多选题和12类时间敏感子集。
- **对比方法**：Video-LLaVA（相同数据混合）、Video-Chat、Video-LLaMA、Video-ChatGPT、SeViLA、LLaMA-VID（7B/13B）等。特别将Video-LLaVA作为基线，因为MERV直接基于其代码修改并使用相同训练数据。

## 4. 资源与算力
- **训练配置**：
  - 使用PyTorch FSDP（全分片数据并行）实现并行化。
  - 在8块L40-48GB GPU上训练<24小时；在8块H100上训练约8小时。
  - MERV（frozen）仅用Stage 2数据，训练时间约为Video-LLaVA原配方的43%。
- **推理**：由于多编码器可在同一GPU上并行提取特征，额外开销较小（图3显示4个编码器比单个编码器步时仅增加约20%）。

## 5. 实验数量与充分性
- **实验组数**：大量消融实验，包括：
  - 预融合投影器选择（2D/3D池化、注意力、卷积等，6种）
  - 输出token长度（1到256个token，8种）
  - 特征融合策略（交叉注意力、序列/通道拼接、可学习权重、固定混合，5种）
  - 训练配方（frozen、full、标准Video-LLaVA配方、混合Stage1+2等，4种）
  - 编码器组合（分别去掉每个编码器，4组；添加Hiera额外实验）
  - 单编码器基线性能对比（4个单独编码器）
  - WH-word任务分析、SSv2时间子集分析等。
- **充分性评价**：实验设计较为全面，涵盖了架构选择、训练策略、编码器贡献等多个维度，且在同一数据混合下与Video-LLaVA公平对比。但在更大规模LLM（如13B）上未做系统测试，且仅在8个公开基准上评估，泛化性验证仍有空间。

## 6. 主要结论与发现
- **性能提升**：在相同数据混合下，MERV（frozen）相比Video-LLaVA在TVQA上提升4.62%，在Perception Test上提升1.99%，在ActivityNet上提升3.79%。MERV（full）在Perception Test上超越SeViLA（48.4% vs 46.2%）。
- **多编码器有效性**：去除任意一个编码器均会导致性能下降（图4a），说明每个编码器都贡献了独特信息。
- **技能专业化**：ViViT在时间敏感的任务（如SSv2时间子集）上表现突出，SigLIP在单帧可推理的类别上更好，MERV成功融合了两者优势。
- **效率**：通过并行化，多编码器带来的额外时间开销很小，FLOPs甚至低于单编码器（因为投影压缩了序列长度）。
- **交叉注意力权重分析**：不同编码器的注意力权重倾向于激活特定类型的视频（如ViViT对运动大的视频权重高，SigLIP对含文本的视频权重高），验证了模型学会了利用各编码器的专长。

## 7. 优点
- **方法创新性**：首次系统探索将多个RGB视觉编码器（而非不同模态）通过空时对齐和交叉注意力融合用于VideoLLM，打破了单一编码器限制。
- **设计高效**：引入轻量级预融合投影器（2D平均池化+线性层），有效压缩序列长度，减少LLM计算负担；并行化策略使得多编码器额外开销极小。
- **公平对比**：严格控制训练数据与Video-LLaVA一致，准确归因性能提升来自多编码器融合。
- **分析深入**：通过SSv2时间子集、WH-word任务、交叉注意力权重可视化等多种定性定量分析，验证了模型对编码器专业技能的吸收。

## 8. 不足与局限
- **计算资源依赖**：尽管并行化高效，但多编码器仍需要更多GPU显存和计算，在资源受限环境下可能不可行。论文提到FSDP的通用分片策略未进行针对性优化。
- **LLM局限**：性能高度依赖于LLaMA-2 7B的能力，若LLM更强（如13B）可能进一步提升，但未实验验证。
- **编码器上限**：如果所选编码器本身在视频理解上有缺陷，MERV无法完全弥补。
- **实验覆盖**：对长视频场景（如MovieChat）未作评估；SSv2数据集上仅用MCQ格式，未做完整原始分类任务。
- **可解释性**：交叉注意力权重提供了部分解释，但融合后的特征是否真正保留了各编码器的互补信息仍需更多验证。

（完）
