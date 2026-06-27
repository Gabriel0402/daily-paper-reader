---
title: Advancing Semantic Future Prediction through Multimodal Visual Sequence Transformers
title_zh: 通过多模态视觉序列Transformer推进语义未来预测
authors: "Karypidis, Efstathios, Kakogeorgiou, Ioannis, Gidaris, Spyros, Komodakis, Nikos"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Karypidis_Advancing_Semantic_Future_Prediction_through_Multimodal_Visual_Sequence_Transformers_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 面向自主系统的多模态语义预测
tldr: 自主系统需要预测动态环境中的未来语义。FUTURIST提出统一的多模态视觉序列Transformer，采用掩码建模和层次化分词，高效融合多种模态信息。在多个预测基准上取得领先性能，对自动驾驶感知有重要意义。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1802, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1644, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 872, \"height\": 198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 838, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 876, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 618, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 707, \"height\": 534, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 873, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 874, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karypidis-advancing-semantic-future-prediction-through-multimodal-visual-sequence-transformers-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 877, \"height\": 231, \"label\": \"Table\"}]"
motivation: 自主系统需要准确的多模态未来语义预测以做出决策。
method: 设计统一视觉序列Transformer，含多模态掩码建模和VAE-free层次分词。
result: 在语义未来预测任务上超过现有方法。
conclusion: 高效多模态融合可提升动态场景的理解与预测能力。
---

## Abstract
Semantic future prediction is important for autonomous systems navigating dynamic environments. This paper introduces FUTURIST, a method for multimodal future semantic prediction that uses a unified and efficient visual sequence transformer architecture. Our approach incorporates a multimodal masked visual modeling objective and a novel masking mechanism designed for multimodal training. This allows the model to effectively integrate visible information from various modalities, improving prediction accuracy. Additionally, we propose a VAE-free hierarchical tokenization process, which reduces computational complexity, streamlines the training pipeline, and enables end-to-end training with high-resolution, multimodal inputs. We validate FUTURIST on the Cityscapes dataset, demonstrating state-of-the-art performance in future semantic segmentation for both short- and mid-term forecasting. We provide the implementation code and model weights at https://github.com/Sta8is/FUTURIST.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：自主系统（如自动驾驶）需要准确预测动态环境的未来状态以做出安全决策。预测原始RGB帧复杂度高、低层细节冗余；直接预测语义信息（如语义分割、深度图）更简洁且直接服务于决策。
- **背景**：现有语义预测方法多基于卷积或循环网络，难以捕捉长距离时空依赖；而基于VAE的Transformer视频生成方法需要为每个模态单独训练VAE，训练不稳定且不适用于多模态场景。
- **核心问题**：如何设计一个统一、高效的Transformer架构，无需VAE即可实现多模态（分割+深度）未来语义预测，并利用模态间的协同效应提升精度。

## 2. 方法论
- **核心思想**：提出FUTURIST，一个**多模态视觉序列Transformer**，将未来预测视为**掩码视觉建模**任务。模型输入多帧（上下文帧）的多模态数据，部分或全部掩码未来帧的令牌，通过自注意力重建被掩码的令牌，从而一次性预测未来帧的所有模态。
- **关键技术细节**：
  - **VAE-free层次化Tokenization**：对每个模态，先通过可训练嵌入矩阵将像素值映射为低维连续嵌入（C<sub>I</sub>=10），再通过线性投影将P×P patch展平为令牌。免去预训练VAE，支持端到端训练。
  - **多模态融合**：将各模态的令牌沿嵌入维度拼接（CONCAT），默认d<sub>S</sub>=d<sub>D</sub>=d/2，减少序列长度，保持计算效率。
  - **多模态掩码策略**：提出“部分共享+独占”（Partially-shared+Exclusive）策略：先采样一个共享掩码，对于共享掩码中可见的令牌，仅让一个模态可见，其余模态仍掩码此位置。避免任何未来帧令牌同时拥有两个模态的可见信息，促进模态间协同学习。
  - **时空分解注意力**：Transformer层交替进行时域注意力（同空间位置跨帧）和空域注意力（同帧内不同空间位置），以降低自注意力的二次复杂度。
  - **端到端训练**：整个模型（嵌入器、Transformer、解码器）通过多模态掩码视觉建模损失联合优化。损失函数为各模态掩码令牌的交叉熵之和（加权）。
- **公式/算法流程**：  
  输入N帧（N<sub>c</sub>上下文+N<sub>p</sub>未来）的多模态数据 → 各模态独立嵌入 → 拼接融合 → 添加位置编码 → 时空Transformer → 各模态解码器（线性层+softmax）输出未来帧预测。训练时仅对掩码令牌计算交叉熵损失。

## 3. 实验设计
- **数据集与场景**：
  - 主要数据集：**Cityscapes**（2,975训练序列，500验证，1,525测试，每序列30帧@16fps，分辨率1024×2048）。使用伪标签：语义分割用**Segmenter**预测，深度用**DepthAnythingV2**预测。
  - 评估场景：**短程预测**（3帧前，0.18s）和**中程预测**（9帧前，0.54s）。帧序列按因子3降采样，5帧输入（4上下文+1未来）。
  - 深度评估：因Cityscapes无真实深度，使用DepthAnythingV2生成的伪标注作为评价参考。
- **基准方法**：
  - 上界：**Oracle**（直接在真实未来帧上运行Segmenter/DepthAnythingV2）。
  - 下界：**Copy-Last**（复制最后上下文帧）。
  - 现有方法：3Dconv-F2F、Dil10-S2S、F2F、DeformF2F、LSTM M2M、F2MF、PFA等。
  - 生成式基线：**VISTA**（2.5B参数的视频扩散模型，在Cityscapes上微调后生成RGB帧，再用Segmenter/DepthAnythingV2提取语义）。
- **评价指标**：语义分割用**mIoU（全部类）** 和**MO-mIoU（可移动对象类）**；深度用**AbsRel（×100）** 和**δ1阈值准确率**。

## 4. 资源与算力
- 训练硬件：**8块NVIDIA A100 40GB GPU**，有效批量大小64。
- 训练时长：最长训练**3200 epochs（147,200次迭代）约32小时**；大多数实验训练**800 epochs**（论文未明确给出总时长，但可推算约8小时）。
- 其他：使用GRNET和GENCI-IDRIS HPC资源（文中致谢部分提及）。

## 5. 实验数量与充分性
- **实验组数**：
  - 主实验：Cityscapes上对比多种SOTA方法，同时报告分割和深度结果。
  - 消融实验：
    - 多模态 vs. 单模态（表2）
    - 训练epoch缩放（图5，400/800/1600/3200 epochs）
    - 序列长度（N=3,4,5,7）（表3）
    - 掩码策略（独立同r/不同r、全共享、部分共享+独占、全掩码）（表4）
    - 融合策略（ADD vs. CONCAT）（表5）
    - 补充材料中还包括：VAE-free与VQ-VAE对比、计算预算公平对比（SepTokens）、SYNTHIA-Seq数据集验证、长时预测可视化。
  - 总体约**10组以上**定量消融，加上定性可视化（图1、6、7）。
- **充分性评估**：
  - **充分**：覆盖关键设计选择（模态、掩码、融合、序列长度、训练规模），且与最先进方法公平对比（包括生成式模型VISTA）。
  - **客观**：所有方法使用相同评价设置，Oracle和Copy-Last上下界清晰。
  - **不足**：深度评价依赖伪标注而非真实深度，可能引入偏差；仅在Cityscapes一个真实数据集上验证（SYNTHIA-Seq为合成数据），泛化性待验证。

## 6. 主要结论与发现
- **性能领先**：FUTURIST在Cityscapes上短程和中程未来语义分割均超越所有现有方法（PFA等），在移动物体类（MO）上尤其显著（短程mIoU 74.9 vs. PFA 69.2）。
- **多模态协同增强**：多模态模型（分割+深度）在分割和深度任务上均优于单模态版本，证明模态间互相促进。
- **训练规模可扩展**：延长训练epochs（至3200）持续提升性能，表明模型能有效利用更多计算资源。
- **掩码策略关键**：部分共享+独占策略最优，全掩码最差，说明适度困难训练促进跨模态学习。
- **VAE-free有效性**：层次化tokenization无需预训练VAE即可达到甚至超越VAE方法，且更简单。
- **与生成式方法对比**：VISTA生成的RGB帧经后处理反而低于Copy-Last，直接预测语义空间更有效。

## 7. 优点
- **架构创新**：首次将Transformer用于多模态未来语义预测，统一处理分割和深度，且免去VAE的繁琐训练。
- **高效融合**：通过令牌拼接实现早期融合，保持低序列长度，利用自然模态相关性提升预测。
- **伪标签训练**：使用预训练基础模型生成伪标签，避免繁琐的人工标注，降低数据门槛，且性能仍达SOTA。
- **端到端可训练**：整个流水线端到端优化，无需分阶段预训练。
- **详尽的消融实验**：系统验证了各组件贡献，结果统计可信。

## 8. 不足与局限
- **数据集局限**：仅使用Cityscapes（单一城市驾驶场景），未在更多样化数据集（如nuScenes、Waymo）上验证，泛化性不确定。
- **深度评估偏差**：Cityscapes缺少真实深度，使用伪标签评价可能放大模型误差或掩盖真实性能。
- **依赖伪标签质量**：伪标签由离线模型生成，若离线模型在复杂场景失败，会引入训练噪声。
- **计算成本仍较高**：尽管无VAE，但32小时8*A100训练对于中等数据集仍显昂贵；且Transformer序列长度随帧数、分辨率线性增长。
- **长期预测能力未充分量化**：仅展示了长时rollout可视化，未提供定量指标（如>1秒的mIoU），且误差会随自回归累积。
- **仅处理两种模态**：论文未验证加入光流、实例分割等更多模态的效果，扩展性待检验。
- **缺乏真实动态场景测试**：伪标签来自静态模型，无法捕捉未来真实变化（如新物体出现），模型可能偏向静态预测。

（完）
