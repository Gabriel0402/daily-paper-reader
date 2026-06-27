---
title: Segment Any-Quality Images with Generative Latent Space Enhancement
title_zh: 通过生成式潜在空间增强分割任意质量图像
authors: "Guo, Guangqian, Guo, Yong, Yu, Xuehui, Li, Wenbo, Wang, Yaoxing, Gao, Shan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Guo_Segment_Any-Quality_Images_with_Generative_Latent_Space_Enhancement_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: SAM模型在低质量图像分割中的应用，使用潜在扩散增强
tldr: SAM在处理低质量图像时性能严重下降。本文提出GleSAM，通过潜在扩散重建高质量特征表示，提升SAM在低质量图像上的鲁棒性，并引入兼容性技术，使分割模型能泛化到各种图像质量。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 841, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 849, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1786, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1741, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 872, \"height\": 273, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1813, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1813, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 880, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 872, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 864, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 849, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-guo-segment-any-quality-images-with-generative-latent-space-enhancement-cvpr-2025-paper/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 828, \"height\": 212, \"label\": \"Table\"}]"
motivation: SAM在低质量图像上性能显著下降，限制实际应用。
method: 在SAM潜在空间中执行扩散过程以重建高质量表示，并设计兼容性技术。
result: 在多种退化图像上分割精度大幅提升，泛化性强。
conclusion: 生成式潜在增强可有效提升SAM对低质量图像的鲁棒性。
---

## Abstract
Despite their success, Segment Anything Models (SAMs) experience significant performance drops on severely degraded, low-quality images, limiting their effectiveness in real-world scenarios. To address this, we propose GleSAM, which utilizes Generative Latent space Enhancement to boost robustness on low-quality images, thus enabling generalization across various image qualities. Specifically, we adapt the concept of latent diffusion to SAM-based segmentation frameworks and perform the generative diffusion process in the latent space of SAM to reconstruct high-quality representation, thereby improving segmentation. Additionally, we introduce two techniques to improve compatibility between the pre-trained diffusion model and the segmentation framework. Our method can be applied to pre-trained SAM and SAM2 with only minimal additional learnable parameters, allowing for efficient optimization. We also construct the LQSeg dataset with a greater diversity of degradation types and levels for training and evaluating the model. Extensive experiments demonstrate that GleSAM significantly improves segmentation robustness on complex degradations while maintaining generalization to clear images. Furthermore, GleSAM also performs well on unseen degradations, underscoring the versatility of our approach and dataset. Codes and datasets will be available soon.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义
**研究动机与背景**  
Segment Anything Models（SAM 和 SAM2）作为基础分割模型，在清晰图像上表现优异，但在实际场景中常见的低质量图像（如噪声、模糊、压缩伪影、混合退化等）上性能显著下降。现有方法（如 RobustSAM）通过蒸馏一致性学习提升鲁棒性，但在严重或复杂退化下仍存在困难。作者分析认为，根本原因是低质量图像在 SAM 潜在空间中的特征含有过多噪声，与高质量特征差距过大，导致一致性学习难以弥合。

**核心问题**：如何让 SAM 在任何质量图像（尤其是严重退化图像）上都能鲁棒分割，同时保持对清晰图像的泛化能力。

**整体含义**：提出 GleSAM，利用生成式潜在空间增强（Generative Latent space Enhancement），将预训练潜在扩散模型（LDM）的生成先验引入 SAM 的潜在特征空间，通过单步去噪重建高质量特征，从而提升分割鲁棒性。

## 2. 论文提出的方法论
### 核心思想
将低质量图像经 SAM 编码器得到的潜在特征视为“噪声版本”，利用预训练的 LDM U-Net 进行单步去噪，生成接近清晰图像特征的高质量表示，再送入解码器得到精确分割掩码。

### 关键技术细节
1. **潜在空间中的单步去噪**  
   利用扩散模型逆过程公式，从低质量特征 \(z_L\) 出发，在时间步 \(T\) 执行一步去噪：
   \[
   \hat{z}_H = \frac{\gamma z_L - \sqrt{1 - \bar{\alpha}_T} \epsilon_\theta(\gamma z_L; T)}{\gamma \sqrt{\bar{\alpha}_T}}
   \]
   其中 \(\gamma\) 为特征分布对齐权重，\(\epsilon_\theta\) 为预训练 U-Net（添加 LoRA 可训练层）。

2. **特征分布对齐（FDA, Feature Distribution Alignment）**  
   由于 SAM 潜在空间与 LDM 的 VAE 潜在空间分布差异大，直接输入 U-Net 效果差。引入缩放因子 \(\gamma\) 调整特征方差，使分布更匹配 U-Net 输入空间，去噪后再除以 \(\gamma\) 恢复原始分布。

3. **通道复制与扩展（CRE, Channel Replicate and Expansion）**  
   LDM 的 U-Net 输入/输出为 4 通道，而 SAM 潜在特征为 256 通道。通过复制预训练 U-Net 首尾层的权重并拼接以匹配通道数，保持预训练参数冻结，仅添加 LoRA 层微调。避免从头训练新层导致的性能退化。

4. **两阶段微调**  
   - **第一阶段**：冻结图像编码器和 U-Net 主体，仅训练 LoRA 层，用重建损失 \(\mathcal{L}_{\text{Rec}} = \text{MSE}(\hat{z}_H, z_H)\) 优化 U-Net 输出与真实高质量特征的对齐。  
   - **第二阶段**：冻结图像编码器和 U-Net，微调解码器（或仅 mask token），用分割损失 \(\mathcal{L}_{\text{Seg}} = \mathcal{L}_{\text{Dice}} + \mathcal{L}_{\text{Focal}}\) 训练，使增强特征适应分割任务。

5. **数据与退化模型**  
   构建 LQSeg 数据集：从 LVIS、ThinObject-5K、MSRA10K 生成低质量图像，退化过程包括随机组合的模糊、重采样、噪声、JPEG 压缩，并设置三个退化级别（LQ-1 轻度，LQ-2 中度，LQ-3 重度），通过调整下采样率实现。

## 3. 实验设计
### 数据集与场景
- **训练集**：LVIS 训练集、ThinObject-5K 训练集、MSRA10K（合成退化）。
- **评估集**：
  - **已见数据集（seen）**：ThinObject-5K 测试集、LVIS 测试集（三个退化级别）。
  - **未见数据集（unseen）**：ECSSD、COCO-val（三个退化级别）。
  - **其他退化类型**：RobustSeg 风格退化（混合退化，未在训练中使用），用于测试泛化。

### Benchmark 与对比方法
- **SAM 系列**：原始 SAM、SAM2、RobustSAM（专为退化图像设计的 SAM 变体）。
- **两阶段方法**：先用图像修复网络（PromptIR、DiffBIR）恢复图像，再输入 SAM/SAM2 分割。
- 评价指标：IoU、Dice、Pixel Accuracy。

### 实验结果概要
- 在已见和未见数据集上，GleSAM 和 GleSAM2 在所有退化级别均显著优于所有对比方法，尤其在 LQ-3 最严重退化下提升最大（例如 ThinObject-5K LQ-3 上，GleSAM IoU 0.7594 vs SAM 0.6285）。
- 在 RobustSeg 风格退化上（未见过），GleSAM 仍优于 RobustSAM（后者专门在类似退化上训练），证明了很强的泛化性。
- 消融实验验证了每个组件的有效性（Gle+CRE+FDA 相比基线大幅提升）。
- 微调解码器时，直接微调 SAM 解码器在清晰图像上性能大幅下降（IoU 下降约 20 点），而 GleSAM 微调后低质量和清晰图像均提升。
- 通道扩展方法对比：CRE 优于添加额外卷积层或从零训练新首尾层。
- 超参数 \(\gamma\) 实验：最佳值为 5。
- LoRA 秩分析：秩 8 取得最佳平衡。
- 多级别退化联合训练优于单独级别训练。

## 4. 资源与算力
文中明确说明：
- GPU：4 × A100。
- 训练时长：约 30 小时（U-Net 微调 100K 迭代，解码器微调 20K 迭代）。
- 参数量：GleSAM 额外可学习参数仅 47 MB（相比 SAM 的 1250 MB）；推理速度仅增加约 0.06 秒/张（从 0.32 s 到 0.38 s）。

## 5. 实验数量与充分性
- **主实验**：2 个已见数据集 × 3 级别 + 2 个未见数据集 × 3 级别，共 12 个设置，结果表格清晰。
- **零样本泛化实验**：在 RobustSeg 退化上测试，共 2 个数据集。
- **消融实验**：组件消融（Tab.4）、微调策略消融（Tab.5）、通道扩展方法对比（Tab.6）、超参数 \(\gamma\) 分析（Fig.6）、LoRA 秩（Tab.8）、退化级别训练策略（Tab.7）。
- **可视化**：特征可视化（Fig.2、Fig.5、Fig.7）、IoU-图像质量密度图（Fig.4）、定性分割结果（Fig.1）。
- 实验设计较为全面，对比方法包括当前最优的退化分割方法和图像修复+SAM 组合，公平性较好。但未对比其他基于扩散的分割增强方法（如直接使用扩散模型作为 backbone 的方法），可能因方法路线不同。

## 6. 论文的主要结论与发现
- 将预训练潜在扩散模型的生成先验融入 SAM 潜在空间，通过单步去噪重建高质量特征，可显著提升低质量图像分割精度，同时保持清晰图像上的泛化性。
- 提出的 FDA 和 CRE 技术有效解决了跨模型特征分布和结构不匹配问题。
- LQSeg 数据集包含多类型多级别退化，有助于训练和评估鲁棒分割模型。
- GleSAM 在未见退化上表现优异，证明其适应性和通用性。

## 7. 优点
1. **方法创新性**：首次将潜在扩散的单步去噪引入 SAM 的特征增强，而非单纯作为图像预处理或 backbone。
2. **高效性**：仅添加少量可学习参数（LoRA），训练快速（30h/4GPU），推理开销极小（+0.06s）。
3. **兼容性好**：可直接应用于 SAM 和 SAM2，无需修改原架构。
4. **数据集贡献**：LQSeg 覆盖多种退化类型和级别，有助于推动该方向研究。
5. **实验充分**：覆盖多种退化、多级别、零样本泛化、详细消融，结果可信度高。
6. **分析与可视化**：通过特征热力图、密度图直观展示增强效果。

## 8. 不足与局限
1. **实验覆盖范围**：主要评估了物体级分割（实例/显著性），未测试语义分割或全景分割等任务，通用性待验证。
2. **退化类型限制**：虽然包含多种退化，但均为合成退化，真实世界低质量图像（如传感器噪声、运动模糊、水下退化等）可能仍有差距。
3. **依赖单独训练阶段**：需要重建损失和分割损失两阶段训练，流程稍复杂，可能影响调优效率。
4. **单步去噪假设**：将低质量特征视为噪声版本，但实际退化可能并非高斯噪声，该方法在非加性退化下效果可能打折扣。
5. **未与更多扩散感知方法对比**：如 VPD、DDP 等，可能因任务差异，但缺少直接竞争比较。
6. **潜在偏差**：LQSeg 训练数据来源于特定数据集（LVIS、ThinObject-5K、MSRA10K），若目标域差异过大，泛化性可能下降。

（完）
