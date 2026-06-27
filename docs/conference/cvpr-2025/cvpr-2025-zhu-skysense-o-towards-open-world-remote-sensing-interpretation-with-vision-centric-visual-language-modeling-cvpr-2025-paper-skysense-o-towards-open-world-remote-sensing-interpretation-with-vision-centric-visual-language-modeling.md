---
title: "SkySense-O: Towards Open-World Remote Sensing Interpretation with Vision-Centric Visual-Language Modeling"
title_zh: SkySense-O：面向开放世界遥感解译的以视觉为中心的视觉语言建模
authors: "Zhu, Qi, Lao, Jiangwei, Ji, Deyi, Luo, Junwei, Wu, Kang, Zhang, Yingying, Ru, Lixiang, Wang, Jian, Chen, Jingdong, Yang, Ming, Liu, Dong, Zhao, Feng"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhu_SkySense-O_Towards_Open-World_Remote_Sensing_Interpretation_with_Vision-Centric_Visual-Language_Modeling_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 遥感图像语义分割结合视觉语言模型
tldr: 现有遥感语义分割面临类别有限和空间分布密集的挑战。本文提出SkySense-O，采用以视觉为中心的视觉语言建模，构建细粒度数据集Sky-SA，实现了开放世界遥感图像中所有物体的定位与识别，显著提升了分割精度和泛化能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 873, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 848, \"height\": 252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1801, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 863, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 866, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 859, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 867, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 854, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1807, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 867, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 868, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 869, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 862, \"height\": 525, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 873, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1037, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1813, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 743, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 875, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-skysense-o-towards-open-world-remote-sensing-interpretation-with-vision-centric-visual-language-modeling-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 299, \"label\": \"Table\"}]"
motivation: 现有遥感语义分割类别有限且空间分布密集，难以区分多样区域。
method: 构建细粒度遥感数据集Sky-SA，并采用以视觉为中心的视觉语言模型进行开放世界分割。
result: 在多个遥感数据集上取得优异分割性能，尤其对细粒度类别表现突出。
conclusion: 视觉中心方法能有效提升遥感开放世界分割的准确性和泛化性。
---

## Abstract
Open-world interpretation aims to accurately localize and recognize all objects within images by vision-language models (VLMs). While substantial progress has been made in this task for natural images, the advancements for remote sensing (RS) images still remain limited, primarily due to these two challenges. 1) Existing RS semantic categories are limited, particularly for pixel-level interpretation datasets. 2) Distinguishing among diverse RS spatial regions solely by language space is challenging due to the dense and intricate spatial distribution in open-world RS imagery. To address the first issue, we develop a fine-grained RS interpretation dataset, Sky-SA, which contains 183,375 high-quality local image-text pairs with full-pixel manual annotations, covering 1,763 category labels, exhibiting richer semantics and higher density than previous datasets. Afterwards, to solve the second issue, we introduce the vision-centric principle for vision-language modeling. Specifically, in the pre-training stage, the visual self-supervised paradigm is incorporated into image-text alignment, reducing the degradation of general visual representation capabilities of existing paradigms. Then, we construct a visual-relevance knowledge graph across open-category texts and further develop a novel vision-centric image-text contrastive loss for fine-tuning with text prompts. This new model, denoted as SkySense-O, demonstrates impressive zero-shot capabilities on a thorough evaluation encompassing 14 datasets over 4 tasks, from recognizing to reasoning and classification to localization. Specifically, it outperforms the latest models such as SegEarth-OV, GeoRSCLIP, and VHM by a large margin, i.e., 11.95%, 8.04% and 3.55% on average respectively.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有遥感（RS）解译模型难以实现开放世界能力，主要面临两大挑战：（1）现有遥感语义分割数据集类别有限，尤其缺乏细粒度、密集像素级别的开放文本标注；（2）遥感图像中地物分布密集且空间结构复杂，仅依靠语言空间难以有效区分多样化的地物类别，导致视觉-语言对齐出现歧义。
- **研究动机**：受自然图像领域（如SA-1B、COCO-Stuff）成功经验的启发，旨在构建一个大规模、高质量、开放文本的遥感像素级标注数据集，并设计一种以视觉为中心的视觉-语言建模策略，提升模型在开放世界场景下的零样本泛化能力。
- **整体含义**：论文提出的SkySense-O模型，从数据集到训练策略全面推动了遥感开放世界解译的发展，使模型能够同时进行物体分割、土地覆盖分割、场景分类和视觉问答等多种任务。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- **以视觉为中心的视觉-语言建模（Vision-Centric Modeling）**：针对语言引导可能带来的对齐歧义，强调优先利用视觉表征能力，减少视觉退化，并通过构建视觉相关性知识图谱来修正正负样本采样。
- **从数据到模型的完整流程**：包括大规模开放文本数据集构建（Sky-SA）、预训练对齐、基于知识图谱的微调与正则化。

### 关键技术细节
1. **Sky-SA数据集构建**：
   - 从多个公开遥感数据集收集35,000张图像，利用SkySense模型筛选冗余图片。
   - 采用GPT-4V生成图像内容描述、Grounding-DINO和SAM进行预标注，人工修正。
   - 最终包含183,375个段-文本对，覆盖1,763个类别标签（经同义词过滤后约500个不同类别），实现全像素密集标注 → 首个遥感领域的像素级开放文本数据集。

2. **预训练阶段**：
   - 视觉编码器初始化为SkySense（多模态遥感基础模型）。
   - 在图像-文本对齐训练中，保留视觉自监督范式（掩码图像建模+图像对比学习），防止视觉表征退化。
   - 预训练损失函数：\( \mathcal{L}_{\text{pretrain}} = \text{CE}(x, y) + \text{CE}(x, x') + \text{MR}(I', R') \)，其中CE为交叉熵对比损失，MR为掩码重建损失。
   - 使用大规模RS图像-文本数据集（SkyScript、RS5M等，共1000万对），并用Qwen-VL和InternVL扩充字幕。

3. **微调阶段（区域级和像素级）**：
   - **区域级微调**：基于Sky-SA数据集，对每个掩码区域提取局部特征，计算与对应类别文本的区域级交叉熵损失。
   - **像素级微调**：类似开放词汇语义分割模型，计算图像-文本token级相似度，经视觉解码器上采样得到像素级分割结果，与真实掩码计算像素级交叉熵损失。

4. **以视觉为中心的知识图谱与正则化**：
   - 利用GPT-4V以思维链方式评估每对文本类别之间的视觉相似度（基于外观、形状、颜色等视觉属性），构建知识图谱（节点为类别，边为视觉相关分数及理由）。
   - **文本采样器**：根据视觉相关分数，选择低视觉相似度（但可能具有强上下文关系）的样本作为负样本，避免“路”被错误当作“车”的正样本。
   - **视觉中心正则化损失**：对高文本相似度但低视觉相关度的硬样本施加额外惩罚：\( \mathcal{L}_{vc} = \frac{1}{BN}\sum \left[(1 - S^v) \cdot S^t \cdot \mathcal{L}_{\text{region}}\right]^2 \)，其中\(S^t\)为文本相似度，\(S^v\)为视觉相关分数。
   - 总微调损失：\( \mathcal{L}_{\text{finetune}} = \mathcal{L}_{\text{pixel}} + \lambda_1 \mathcal{L}_{\text{region}} + \lambda_2 \mathcal{L}_{vc} \)，超参数\(\lambda_1=\lambda_2=0.4\)（通过消融实验确定）。

## 3. 实验设计：数据集、benchmark、对比方法

### 评估任务与数据集（共14个数据集，4项任务）
- **零样本物体分割**：iSAID, FAST, SIOR, SOTA（共4个）
- **零样本土地覆盖分割**：ISPRS Potsdam, Vaihingen, FloodNet, OpenEarthMap (OEM), LoveDA（共5个）
- **零样本场景分类**：AID, RESISC-45（共2个）
- **零样本视觉问答 (VQA)**：SIRI-WHU, AID-VQA, RSVQA-HR（共3个）

### 对比方法
- **物体/土地覆盖分割**：SegGPT（少样本）、DINOv（少样本）、SAN、CAT-SEG、SegEarth-OV等。
- **场景分类**：CLIP、RemoteCLIP、GeoRSCLIP、SkyScript等。
- **VQA**：GeoChat、LHRS-Bot、EarthGPT、VHM等。

### 实验结果概要
- 姿态零样本物体分割：平均优于SOTA方法14.27% mIoU。
- 土地覆盖分割：在所有数据集上最佳，Potsdam和Vaihingen上超过CAT-SEG 1.41% mIoU。
- 场景分类：在RESISC-45上Top-1准确率83.28%（+9.38%），AID上82.93%（+6.66%）。
- VQA：整合为LLaVA-1.5架构的视觉编码器后，在三个VQA数据集上平均优于VHM 3.55%以上。

## 4. 资源与算力

- **预训练阶段**：使用80张NVIDIA A100-80GB GPU。
- **微调阶段**：使用8张NVIDIA A100-80GB GPU。
- **训练数据规模**：预训练1000万图像-文本对；微调使用Sky-SA（183K对）及OSM数据。
- **训练时长**：文中未明确说明总训练时长，但指出预训练和微调均在大规模GPU集群上进行。

## 5. 实验数量与充分性

### 实验数量
- 涵盖4项任务、14个零样本下游数据集，加上VQA任务中的额外3个数据集（整合到MLLM后）。
- 消融实验：在iSAID上进行了4组消融（基线、加Sky-SA、加知识图谱、加预训练、加正则化），验证各组件贡献。
- 额外分析：比较Sky-SA与其他数据集（COCO-Stuff、Potsdam训练集等）的零样本泛化能力。

### 充分性、客观性与公平性
- **充分性**：实验覆盖了遥感解译的主要任务，数据集多样（包含不同分辨率、不同地物类型），对比方法包括最新少样本和零样本方法，消融实验完整。
- **客观性**：均遵循零样本设置，不使用下游数据训练；报告标准指标（mIoU、Top-1准确率、准确率）。
- **公平性**：对比方法均采用官方或公开代码/报告结果；SkySense-O的视觉编码器参数量较大（SwinV2-H-8，654M），但论文在表5中主动列出了模型规模与数据规模差异，承认缩放定律的影响。

## 6. 论文的主要结论与发现

- **数据集关键性**：Sky-SA数据集因其大规模、开放文本、全像素标注的特性，显著提升了开放世界零样本分割性能（替代COCO-Stuff后mIoU提升9.36%）。
- **视觉中心建模有效性**：通过保留视觉自监督、构建视觉知识图谱、引入视觉中心正则化，有效解决了语言上下文导致的误对齐问题，逐步提升性能（从18.40%到43.92%）。
- **通用性突破**：SkySense-O在零样本场景下全面超越现有SOTA，甚至在物体分割任务上超过少样本方法，表明开放世界解译模型已具备实用潜力。
- **智能体应用**：作为视觉编码器嵌入MLLM后，显著提升视觉问答准确性，展示了作为智能体基础模型的潜力。

## 7. 优点

1. **数据集创新**：首个遥感领域像素级开放文本数据集，类别数（1,763）远超现有分割数据集，且支持“填空式”标注而非预设列表。
2. **方法论亮点**：首次在遥感视觉语言建模中引入“以视觉为中心”原则，提出知识图谱+正则化损失，巧妙解决了高上下文依赖类别的判别难题。
3. **实验全面性**：横向覆盖4项主流任务，纵向深入消融每个组件；可视化展示了图像-文本对齐图（TIR maps）和知识图谱社区结构，直观验证方法有效性。
4. **性能卓越**：在14个数据集上平均超过SegEarth-OV 11.95%、GeoRSCLIP 8.04%、VHM 3.55%，且部分结果超过少样本方法。
5. **开源与复现**：代码公开，便于后续研究。

## 8. 不足与局限

1. **实验覆盖的偏差风险**：尽管数据集多样，但主要集中于光学遥感图像，缺乏对SAR、多光谱等模态的验证，可能限制在特定遥感任务上的泛化性。
2. **资源需求高**：模型参数量大（654M），预训练需要80卡A100，微调需要8卡，对硬件要求较高，不利于低资源研究落地。
3. **训练时长未披露**：论文未提供训练时间，难以评估方法在计算效率上与对比方法的差距。
4. **语义层次限制**：知识图谱基于GPT-4V构建，依赖第三方模型，可能引入固有偏见或对某些稀有类别的视觉属性描述不准确；且仅使用0.5阈值进行正负采样，可能未充分优化图结构。
5. **同义词过滤后实际类别数约500**：虽远多于以往，但与自然图像领域（如COCO-Stuff的171类）相比，类别多样性仍有差距。
6. **仅在零样本设置下评估**：未进行少样本或全监督场景的实验，无法全面评估模型在标注数据受限情况下的灵活性与优势。

（完）
