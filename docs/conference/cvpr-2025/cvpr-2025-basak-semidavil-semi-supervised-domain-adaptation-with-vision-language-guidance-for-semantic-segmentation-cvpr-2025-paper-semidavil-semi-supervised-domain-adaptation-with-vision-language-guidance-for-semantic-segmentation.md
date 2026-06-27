---
title: "SemiDAViL: Semi-supervised Domain Adaptation with Vision-Language Guidance for Semantic Segmentation"
title_zh: SemiDAViL：基于视觉语言引导的半监督域适应语义分割
authors: "Basak, Hritam, Yin, Zhaozheng"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Basak_SemiDAViL_Semi-supervised_Domain_Adaptation_with_Vision-Language_Guidance_for_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 使用视觉语言模型的半监督域适应语义分割
tldr: 半监督域适应语义分割面临类别混淆和训练偏斜问题。本文提出SemiDAViL，利用视觉语言指导增强目标域特征判别，通过VLM提供的语义先验缓解相似外观类别的误分，在不平衡数据集上表现优异。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 648, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 481, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 878, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 879, \"height\": 845, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1908, \"height\": 738, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-basak-semidavil-semi-supervised-domain-adaptation-with-vision-language-guidance-for-semantic-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1907, \"height\": 515, \"label\": \"Table\"}]"
motivation: 简单结合域适应与半监督学习在语义分割中效果不佳，易混淆类别且数据偏斜。
method: 引入视觉语言模型生成类别描述，作为语义引导辅助分割网络训练。
result: 在多个域适应基准上超越了现有方法。
conclusion: 视觉语言引导有效提升了域适应分割的鲁棒性。
---

## Abstract
Domain Adaptation (DA) and Semi-supervised Learning (SSL) converge in Semi-supervised Domain Adaptation (SSDA), where the objective is to transfer knowledge from a source domain to a target domain using a combination of limited labeled target samples and abundant unlabeled target data. Although intuitive, a simple amalgamation of DA and SSL is suboptimal in semantic segmentation due to two major reasons: (1) previous methods, while able to learn good segmentation boundaries, are prone to confuse classes with similar visual appearance due to limited supervision; and (2) skewed and imbalanced training data distribution preferring source representation learning whereas impeding from exploring limited information about tailed classes. Language guidance can serve as a pivotal semantic bridge, facilitating robust class discrimination and mitigating visual ambiguities by leveraging the rich semantic relationships encoded in pre-trained language models to enhance feature representations across domains. Therefore, we propose the first language-guided SSDA setting for semantic segmentation in this work. Specifically, we harness the semantic generalization capabilities inherent in vision-language models (VLMs) to establish a synergistic framework within the SSDA paradigm. To address the inherent class-imbalance challenges in long-tailed distributions, we introduce class-balanced segmentation loss formulations that effectively regularize the learning process. Through extensive experimentation across diverse domain adaptation scenarios, our approach demonstrates substantial performance improvements over contemporary state-of-the-art (SoTA) methodologies.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：半监督域适应（SSDA）旨在结合少量标注目标域样本和大量未标注目标域数据，将知识从源域迁移至目标域。在语义分割任务中，简单的 DA+SSL 组合效果不佳。
- **核心问题**：
  1. **类别混淆**：由于目标域标注有限，模型容易混淆视觉外观相似的类别（如 fence、pole、wall）。
  2. **训练偏斜**：源域数据充足使模型偏向于源域特征学习，而目标域中长尾（tail）类别难以被充分探索，加剧类别不平衡。
- **研究动机**：利用视觉语言模型（VLM）的丰富语义关系作为语义桥梁，增强不同域间的特征判别能力，同时设计动态类别平衡损失以缓解长尾分布问题。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：构建语言引导的 SSDA 框架 **SemiDAViL**，通过预训练 VLM（CLIP）提取视觉与语言的联合嵌入，并引入密集语言引导模块融合跨模态特征；采用学生-教师网络进行一致性训练，并设计动态交叉熵损失（DyCE）适应类分布变化。
- **关键技术细节**：
  1. **视觉语言预训练 (VLP)**：使用 CLIP 的视觉编码器 \(E_V\) 和语言编码器 \(E_L\) 进行初始化，替代传统的 ImageNet 预训练，以获得更丰富的语义先验。
  2. **密集语言引导 (DLG)**：
     - 从图像 \(X\) 中提取视觉特征 \(F_V \in \mathbb{R}^{h \times w \times c}\)（通过学生/教师视觉编码器）。
     - 使用 off-the-shelf 字幕模型（如 BLIP-2）生成文本描述，再由语言编码器提取语言特征 \(F_L \in \mathbb{R}^{n_L \times c}\)。
     - 将视觉和语言特征投影为键-值对，计算跨模态注意力矩阵 \(A \in \mathbb{R}^{n_L \times h \times w}\)，分别生成语言注意的视觉特征和视觉注意的语言特征，最终融合为多模态特征 \(F_M\)。
  3. **一致性训练 (CT)**：
     - 学生和教师网络各自生成多模态特征并通过相同结构的解码器得到预测 \(y^S, y^T\)。
     - 对未标注目标数据，在预测置信度超过阈值 \(Th=0.95\) 的像素上计算一致性损失 \(L_{CT}\)。
     - 教师网络通过学生参数的指数移动平均（EMA, \(\alpha=0.999\)）更新。
  4. **动态交叉熵损失 (DyCE)**：
     - 标准 CE 损失对所有类别给予同等梯度权重，易导致梯度消失和类别非均衡。
     - DyCE 从每批次中选取 \(h\%\) 最难样本组成子集 \(H\)，按子集中各类出现频率 \(f_c\) 动态分配权重：
       \[
       L_{\text{DyCE}} = -\frac{1}{f_H^\omega} \sum_{c=0}^{N_C} \frac{1}{f_c^{(1-\omega)}} \sum_{i \in H} y_{i,c} \log p_{i,c}
       \]
       其中 \(\omega \in (0,1)\) 平衡实例级与类别级权重，\(f_H=|H|\)。梯度幅值增大，缓解梯度消失。
     - 该损失应用于源域和标注目标域的监督信号 \(L_S\)（替换标准 CE）。

## 3. 实验设计：数据集、基准及对比方法

- **数据集**：
  - **GTA5 → Cityscapes**：合成数据 GTA5（24966 张图像）→ 真实城市街景 Cityscapes（2975 训练 +500 验证，19 类）。
  - **Synthia → Cityscapes**：合成数据 Synthia（9400 张全标注图像）→ Cityscapes（16 类重叠）。
  - **Synapse 医学数据集**：30 个 CT 扫描，13 个器官（前景仅占 4.37%，严重长尾）。用于验证 DyCE 在 SSL 场景下的可迁移性。
- **基准设置**：报告不同标注目标样本数量（0、100、200、500、1000、2975）下的 mIoU（平均交并比）。
- **对比方法**：
  - **UDA 方法**：DeepLabV2、DaCS、DACS、ProDA、CPSL、DAFormer、DIGA 等。
  - **SSL 方法**：CowMix、ClassMix、CPS、DusPerb、ASS、DECOTA 等。
  - **SSDA 方法**：DLDM、SSDDA、DSTC、S-Depth、IIDM、ALFSA、SS-ADA+UniMatch/U2PL 等。
- **消融实验**：对 CT、DyCE、VLP、DLG 四个组件进行逐项消融，分析贡献。
- **类间细节分析**：展示 19 类/16 类的逐类 mIoU，特别关注 tail 类别（如 fence、wall、pole）。
- **DyCE 迁移实验**：在 Synapse 上将 DyCE 作为插件应用于多种 SSL 方法（UA-MT、URPC、DePL、DHC、A&D），报告 DSC 和 ASD 提升。

## 4. 资源与算力

- **硬件**：单张 NVIDIA RTX 4090 GPU（文中明确提及）。
- **训练时间**：约 15 小时完成 40k 迭代（batch size 等未详细说明）。
- **环境**：Python，PyTorch。
- **缺失信息**：未提及是否使用多卡并行、显存占用或具体 batch size，也未公布超参数搜索的具体成本。

## 5. 实验数量与充分性

- **实验组数**：
  - 两个主要域适应 benchmark（GTA5→Cityscapes 和 Synthia→Cityscapes）各报告 6 个标注比例结果。
  - 消融实验 4 个组件 × 4 个标注比例（100/200/500/1000）= 16 组。
  - 类间详细对比表（Table 4）展示两个基准下 100 标注样本的 19 类/16 类结果。
  - 额外 Synapse 实验：6 种 SSL 方法 ± DyCE，报告 14 个器官的 DSC。
  - 定性结果图（Fig.4）展示了改进效果。
- **充分性与公平性**：
  - 对比方法覆盖了主流 UDA、SSL、SSDA 类别，且统一标注数量设置。
  - 消融实验清晰揭示各模块增量贡献。
  - DyCE 在完全不相关的医学分割任务上验证了泛化能力。
  - 未评估真实→真实域（如 Cityscapes 到其他城市）或更高分辨率场景；未报告统计显著性检验。

## 6. 论文的主要结论与发现

- 语言引导能有效缓解 SSDA 中视觉相似类别的误分类，提升特征判别性。
- 提出的 DyCE 损失通过动态加权 tail 类别，在长尾场景（如 Synapse）中带来显著 DSC 提升（最高 +27.9%）。
- 在 GTA5→Cityscapes 上，100 标注样本下达到 71.1% mIoU，超越先前最优 IIDM（69.5%）1.6%；全标注（2975 样本）下达到 75.2%，优于 IIDM 1.9%。
- 在 Synthia→Cityscapes 上，100 标注样本下达到 76.9% mIoU，优于先前最优 IIDM（74.2%）2.7%。
- 消融显示 DLG 与 VLP 贡献最大，DyCE 在保持总体性能的同时显著改善 tail 类。
- 框架具有通用性，DyCE 可即插即用于其他 SSL 方法。

## 7. 优点

- **首次将语言指导引入 SSDA 语义分割**：通过 VLM 提供超越视觉的语义先验，从根本上缓解视觉歧义。
- **密集语言引导模块设计巧妙**：同时利用视觉和语言特征计算双向注意力，生成真正多模态特征，而非简单重新组织单模态。
- **动态类别平衡损失 DyCE**：从梯度层面动态调整尾类权重，避免梯度消失，且无需额外超参数搜索（仅 \(\omega\) 一个）。
- **实验全面**：覆盖多种标注比例、多类方法对比、消融、类间细节、额外医学验证，结果可靠。
- **性能显著**：在多个 benchmark 和标注水平下均超越 SOTA，尤其是在低标注场景下提升明显。

## 8. 不足与局限

- **依赖外部模型**：需要预训练 CLIP 和 BLIP-2 等 VLM/caption 模型，其质量直接影响框架性能；若目标域图像风格与预训练数据差异大，caption 可能不准确。
- **域适应场景单一**：仅测试合成→真实（GTA5/Synthia→Cityscapes），未探索真实→真实（如不同城市间）或恶劣天气等更复杂域迁移。
- **忽略跨域标注空间不匹配**：如 GTA5 与 Cityscapes 的类别标签空间存在细微差异，文中未专门处理。
- **计算/memory 开销细节不足**：虽然训练时间给出，但未比较推理速度、参数量或显存占用 vs. 其他 SOTA。
- **DyCE 的 \(\omega\) 选择**：文中未讨论其敏感性或在其他任务上的最佳范围；实验仅固定一个值。
- **验证集使用**：Cityscapes 验证集同时用于超参数调整和最终测试，可能引入轻微过拟合。
- **未提供统计显著性**：单次实验，未报告多次运行均值与方差。
- **应用限制**：适用于有限标注的视觉分割，对于无标注的完全无监督域适应（UDA）或零样本场景不直接适用。

（完）
