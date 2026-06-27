---
title: "ROS-SAM: High-Quality Interactive Segmentation for Remote Sensing Moving Object"
title_zh: ROS-SAM：面向遥感移动目标的高质量交互分割
authors: "Shan, Zhe, Liu, Yang, Zhou, Lei, Yan, Cheng, Wang, Heng, Xie, Xia"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Shan_ROS-SAM_High-Quality_Interactive_Segmentation_for_Remote_Sensing_Moving_Object_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: SAM模型在遥感分割中的应用
tldr: 遥感视频中移动目标交互分割面临目标小、特征模糊和泛化难等问题。本文提出ROS-SAM，基于SAM通过三项关键创新实现高质量分割：LoRA微调保持SAM泛化能力；增强网络深层特征判别力；以及针对移动目标的特定处理。实验表明ROS-SAM在多个遥感数据集上实现了高精度交互分割，且保持良好的跨域泛化能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 809, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1534, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 728, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 737, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 719, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1605, \"height\": 1513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 841, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 884, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 602, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 444, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 698, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 783, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 762, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-shan-ros-sam-high-quality-interactive-segmentation-for-remote-sensing-moving-object-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 737, \"height\": 338, \"label\": \"Table\"}]"
motivation: 遥感视频中移动目标小而模糊，现有交互分割方法泛化能力有限。
method: 基于SAM框架，采用LoRA微调并增强深层特征判别力，适配遥感移动目标。
result: 在多个遥感数据集上取得高精度交互分割结果，且泛化良好。
conclusion: LoRA微调SAM可有效提升遥感目标分割的质量与泛化性。
---

## Abstract
The availability of large-scale remote sensing video data underscores the importance of high-quality interactive segmentation. However, challenges such as small object sizes, ambiguous features, and limited generalization make it difficult for current methods to achieve this goal. In this work, we propose ROS-SAM, a method designed to achieve high-quality interactive segmentation while preserving generalization across diverse remote sensing data. The ROS-SAM is built upon three key innovations: 1) LoRA-based fine-tuning, which enables efficient domain adaptation while maintaining SAM's generalization ability, 2) Enhancement of network deep layers to improve the discriminability of extracted features, thereby reducing misclassifications, and 3) Integration of global context with local boundary details in the mask decoder to generate high-quality segmentation masks. Additionally, we redesign the data pipeline to ensure the model learns to better handle objects at varying scales during training while focusing on high-quality predictions during inference. Experiments on remote sensing video datasets show that the data pipeline boosts the IoU by 6%, while ROS-SAM increases the IoU by 13%. Finally, when evaluated on existing remote sensing object tracking datasets, ROS-SAM demonstrates impressive zero-shot capabilities, generating masks that closely resemble manual annotations. These results confirm ROS-SAM as a powerful tool for fine-grained segmentation in remote sensing applications. Code is available at: https://github.com/ShanZard/ROS-SAM.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：遥感视频中的移动目标（如飞机、汽车、船只、火车）具有目标尺寸小、特征模糊、密度高、标注成本高等特点，现有交互式分割方法（如SAM）在遥感数据上表现不佳：无法有效区分目标与背景（如飞机与登机桥、船与波浪），预测掩码边界粗糙、碎片化，且固定输入分辨率（1024×1024）导致小目标丢失。
- **动机**：利用已有的大量遥感目标跟踪数据集（只有框标注），通过交互式分割将框转化为高质量分割掩码，从而低成本推进遥感视频分割任务。然而直接使用SAM在遥感场景下效果差，需要针对性适配。
- **整体意义**：提出ROS-SAM，在保持SAM强大泛化能力的同时，实现遥感动目标的高质量交互分割，填补了该领域空白。

#### 2. 方法论
- **核心思想**：基于SAM架构，通过三项创新实现领域适配与高质量预测：1）LoRA微调图像编码器；2）增强深层特征判别性；3）融合全局上下文与局部边界细节的掩码解码器。同时重新设计训练和推理流水线。
- **关键技术细节**：
  - **LoRA微调**：在图像编码器（ViT）的每个Transformer自注意力层的Query和Value投影中插入低秩分解矩阵（编码器 \(W_e \in \mathbb{R}^{r \times n}\)、解码器 \(W_d \in \mathbb{R}^{m \times r}\)），仅更新低秩矩阵参数（秩 \(r \ll \min(m,n)\)），实现参数高效微调。前向传播变为 \(h = W_0 x + W_d W_e x\)。
  - **增强深层特征**：额外解冻图像编码器的最后一个Transformer块，使深层特征更具判别力，减少误分类（如区分飞机与登机桥）。
  - **掩码解码器**：采用HQ-SAM的解码器结构，融合早期层的细粒度纹理特征与后期层的全局上下文特征。与HQ-SAM不同，本文不对原始SAM解码器冻结，而是交替优化原始解码器和HQ解码器（HQ解码器在HQSeg-44K数据集上预训练，提供了边缘细节先验）。
  - **训练流水线**：使用大规模抖动（LSJ，缩放0.1~4.0）和随机旋转增强，使模型适应多尺度、无固定方向的目标。损失函数为BCE Loss + Dice Loss。
  - **推理流水线**：根据提示框位置裁剪出N个512×512的patch，用双三次插值上采样到1024×1024，再依次输入模型；输出后根据位置信息拼回原图。上采样率2倍最优，仅推理单个目标提升精度。

#### 3. 实验设计
- **数据集**：
  - 主要训练/评测：SAT-MTB（遥感视频多任务基准，含249个视频，约5万帧，4类移动目标；去除不完整标注后，每视频随机采样1/4帧）。
  - 零样本测试：SatSOT、VISO、OOTB（三个遥感目标跟踪数据集，无分割标注，仅定性评估）。
  - 静态图像数据集：iSAID（15类）、NPWS VHR-10（10类）。
- **Benchmark**：使用IoU和BIoU（边界IoU）作为评估指标。
- **对比方法**：SAM（ViT-L版本）、SAM2、HQ-SAM；其他适配方法（如SAM-Adapter等）因性能差未列入。

#### 4. 资源与算力
- **未明确说明**：论文未提及使用的GPU型号、数量、训练时长等具体算力信息。仅提到训练48个epoch，学习率1e-3。

#### 5. 实验数量与充分性
- **实验组数**：
  - 消融实验：推理流水线（2种模型×多设置）、训练流水线（LSJ/随机旋转）、掩码解码器（原始/仅HQ/交替优化）、图像编码器（LoRA+解冻最后一层）。
  - 对比实验：在SAT-MTB上与SAM、SAM2、HQ-SAM比较（表5）。
  - 静态图像实验：iSAID、NPWS VHR-10（表6）。
  - 零样本定性实验：三个跟踪数据集（图8）。
- **充分性评价**：消融实验较为全面，覆盖了方法三大组件及数据流水线；对比方法选择合理（包括最新SAM2）；在多个数据集上进行验证（视频+静态+零样本），证明泛化性。但缺乏与更多遥感专用分割方法的比较（论文提到其他方法性能差未展示），且未进行统计显著性检验。总体而言，实验设计客观公平，结果清晰。

#### 6. 主要结论与发现
- 推理流水线可在SAM上提升IoU约6%（从37.25%到43.41%），ROS-SAM整体相比SAM提升13%（50.54% vs 37.25%）。
- 训练流水线中，LSJ比随机旋转贡献更大（+0.6% vs +0.3%）。
- 交替优化两个解码器优于仅更新HQ解码器（48.16% vs 47.15%）。
- LoRA+解冻最后一层对图像编码器微调效果显著。
- 在静态遥感数据集iSAID和NPWS VHR-10上，ROS-SAM大幅优于SAM/HQ-SAM，证实跨领域泛化能力。
- 在无标注的跟踪数据集上，ROS-SAM零样本生成质量接近人工标注。

#### 7. 优点
- **方法简洁高效**：LoRA微调参数极少，保持SAM泛化；解冻深层特征和HQ解码器融合设计轻量且有效。
- **推理流水线创新**：基于提示框的裁剪上采样策略显著提升小目标分割质量，简单实用。
- **零样本能力强**：在多个不同传感器/分辨率的数据集上表现优异，证明良好的领域泛化性。
- **开源代码**：提供GitHub仓库，便于复现和应用。

#### 8. 不足与局限
- **算力信息缺失**：未报告训练所需GPU型号/数量/时间，影响可复现性评估。
- **对比实验覆盖不足**：仅与SAM系列方法比较，未与遥感专用分割模型（如Mask R-CNN或其他SAM适配变体）进行对比，虽有提及但未展示数据。
- **定量评测范围有限**：零样本仅在跟踪数据集上定性，缺乏定量指标（如IoU），说服力稍弱。
- **特定场景限制**：对特征极模糊的目标（如小汽车仅10像素）或密集场景仍可能出错；模型无法预测肉眼难以分辨的细节（如飞机引擎数量）。
- **数据依赖**：训练数据SAT-MTB规模有限（249视频），可能影响模型在更多样环境下的鲁棒性。

（完）
