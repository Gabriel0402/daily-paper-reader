---
title: "LPOSS: Label Propagation Over Patches and Pixels for Open-vocabulary Semantic Segmentation"
title_zh: LPOSS：基于块与像素标签传播的开放词汇语义分割
authors: "Stojnić, Vladan, Kalantidis, Yannis, Matas, Jiří, Tolias, Giorgos"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Stojnic_LPOSS_Label_Propagation_Over_Patches_and_Pixels_for_Open-vocabulary_Semantic_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 9.0
evidence: 基于VLM的开放词汇语义分割
tldr: 该论文提出LPOSS，一种无需训练的开放词汇语义分割方法。它利用视觉语言模型（VLM）的初始块级预测，通过标签传播（联合优化块间关系）和像素级细化步骤来提升分割精度。由于VLM的块间相似性不如纯视觉模型，作者引入视觉模型来捕捉更好的相似关系。LPOSS在多个基准上达到先进水平，特别是在边界区域表现优异，为无需训练的分割方法提供了新方案。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-stojnic-lposs-label-propagation-over-patches-and-pixels-for-open-vocabulary-semantic-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-stojnic-lposs-label-propagation-over-patches-and-pixels-for-open-vocabulary-semantic-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 678, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-stojnic-lposs-label-propagation-over-patches-and-pixels-for-open-vocabulary-semantic-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1807, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-stojnic-lposs-label-propagation-over-patches-and-pixels-for-open-vocabulary-semantic-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1846, \"height\": 1210, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-stojnic-lposs-label-propagation-over-patches-and-pixels-for-open-vocabulary-semantic-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1496, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-stojnic-lposs-label-propagation-over-patches-and-pixels-for-open-vocabulary-semantic-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1500, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-stojnic-lposs-label-propagation-over-patches-and-pixels-for-open-vocabulary-semantic-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1702, \"height\": 972, \"label\": \"Table\"}]"
motivation: 现有VLM在语义分割中缺乏块间相似性，且受限于块编码器的分辨率。
method: 结合标签传播（块级和像素级）利用视觉模型提升VLM分割预测。
result: 在多个分割基准上达到先进水平，边界精度显著提高。
conclusion: 标签传播可以有效增强VLM的开放词汇分割性能，且无需额外训练。
---

## Abstract
We propose a training-free method for open-vocabulary semantic segmentation using Vision-and-Language Models (VLMs). Our approach enhances the initial per-patch predictions of VLMs through label propagation, which jointly optimizes predictions by incorporating patch-to-patch relationships. Since VLMs are primarily optimized for cross-modal alignment and not for intra-modal similarity, we use a Vision Model (VM) that is observed to better capture these relationships. We address resolution limitations inherent to patch-based encoders by applying label propagation at the pixel level as a refinement step, significantly improving segmentation accuracy near class boundaries. Our method, called LPOSS+, performs inference over the entire image, avoiding window-based processing and thereby capturing contextual interactions across the full image. LPOSS+ achieves state-of-the-art performance among training-free methods, across a diverse set of datasets. Code: https://github.com/vladan-stojnic/LPOSS

---

## 论文详细总结（自动生成）

## 论文详细总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：开放词汇语义分割任务中，视觉-语言模型（VLM）由于训练时只优化跨模态对齐（全局图像-文本匹配），导致其**块级特征缺乏良好的内模态相似性**，且受限于ViT的固定分辨率，直接用于密集预测会得到低质量的分割结果（尤其在边界附近）。
- **背景**：现有方法大多通过滑动窗口独立预测每个窗口，但忽略了全图上下文交互；且仅使用块级预测再上采样，导致精度上限低（Oracle实验显示平均mIoU约85%、Boundary IoU约70%）。
- **整体含义**：LPOSS希望**无需额外训练**，仅通过经典标签传播（Label Propagation）手段，利用视觉模型（如DINO）更好的块间关系，在VLM初始预测基础上进行联合优化，并引入像素级细化，从而提升分割精度和边界质量。

### 2. 论文提出的方法论

#### 核心思想
- 将VLM的初始块级预测（每块独立）看作图上节点的初始标签，通过构建图（节点为patch或pixel，边融合**外观相似性**和**空间邻近性**），执行标签传播，使得最终预测既保留初始信息又满足空间-外观平滑性。
- 分别进行**块级标签传播（LPOSS）**和**像素级标签传播（LPOSS+）**，解决块级低分辨率问题。
- 将特征提取与分类预测解耦：特征提取仍按滑动窗口进行（匹配训练分辨率），但分类预测**联合所有窗口**上的patch进行，从而捕获全图交互。

#### 关键技术细节
1. **图构建（块级）**：
   - 节点：所有滑动窗口的所有patch（共 \(K \times N_P\) 个）。
   - 外观邻接矩阵 \(S_a\)：基于视觉模型（DINO）特征向量的余弦相似度，取k-NN邻居。
   - 空间邻接矩阵 \(S_p\)：基于patch中心位置的高斯距离。
   - 最终邻接矩阵 \(S_P = S_a \odot S_p\)（逐元素相乘）。
2. **标签传播（LPOSS）**：
   - 求解线性系统：\(\hat{Y}_{\text{lposs}} = L^{-1}(S_P) Y_{\text{vlm}}\)，其中 \(L = I - \alpha D^{-1/2} S_P D^{-1/2}\)。
   - 等价于最小化二次代价函数：保持初始预测 + 平滑项。
   - 使用共轭梯度法高效求解（利用稀疏性）。
3. **像素级细化（LPOSS+）**：
   - 将LPOSS输出的像素级预测（上采样后）作为初始预测。
   - 构建像素图：节点为每个像素，空间邻域 \(r \times r\) 内连接，外观相似性基于**Lab颜色空间**的欧氏距离。
   - 再次标签传播得到最终分割 \(\hat{Y}_{\text{lposs+}}\)。
4. **跨窗口联合预测**：
   - 特征提取：每个窗口独立用VLM和VM提取特征（窗口大小224×224，步长112×112）。
   - 预测：将所有窗口的patch合并为一个图，运行一次标签传播，然后分解回各窗口再上采样、融合。

### 3. 实验设计

- **数据集**：8个常用基准：PASCAL VOC、COCO Object、PASCAL Context、PASCAL Context59、COCO Stuff、PASCAL VOC20、ADE20k、Cityscapes。
- **评估指标**：mIoU（主流）和 Boundary IoU（关注边界精度）。
- **对比方法**：
  - 仅用VLM：MaskCLIP、GEM、SCLIP、ClearCLIP。
  - 结合VLM+VM：CLIP-DIY、CLIP-DINOiser、ProxyCLIP、LaVG。
- **消融实验**：
  - Oracle块级分辨率上限实验（下采样ground truth再上采样，显示块级预测的理论上限）。
  - 不同窗口大小和步长的对比（无窗口/大窗口/小窗口/集成）。
  - LPOSS vs LPOSS+ 的对比（mIoU和Boundary IoU）。
  - 将LPOSS+作为DINOv2线性分割的细化后处理（额外验证通用性）。
- **超参数固定**：所有数据集使用相同值（α=0.95, k=400, γ=3.0, σ=100, r=13, τ=0.01），未针对特定数据集调优。

### 4. 资源与算力
- 论文在致谢中提到使用了LUMI超级计算机（EuroHPC）以及e-INFRA CZ项目的支持。
- **未明确说明**所使用的GPU型号、数量或训练时长（因为方法本身是training-free，无需训练，仅需推理时构建图和求解线性系统）。
- 算力主要消耗在特征提取（VLM和DINO推理）以及共轭梯度求解（对全图稀疏线性系统），但文中未报告具体时间或资源开销。

### 5. 实验数量与充分性
- **数量**：在8个数据集上进行了主实验，并附加Oracle实验、窗口策略消融、超参数探究（补充材料提及）、以及跨模型细化实验（DINOv2）。实验组数较多。
- **充分性**：
  - 覆盖了主流开放词汇分割数据集，包括室内（ADE20k）、室外（Cityscapes）、物体中心（VOC/COCO）等。
  - 对比了当前所有训练-free的SOTA方法，且部分方法作者复现确保公平。
  - 消融实验设计合理：单独验证块级传播、像素级传播、窗口大小、以及集成效果。
- **客观性**：均使用了相同特征的VLM（OpenCLIP + MaskCLIP）和VM（DINO），避免因骨干差异导致的不公平。但未比较训练-based方法（属于不同范畴）。

### 6. 论文的主要结论与发现
- **LPOSS+在训练-free方法中达到SOTA**：在8个数据集上平均mIoU 42.1%（优于第二名ProxyCLIP 41.1%），Boundary IoU 32.1%（远超第二名29.5%）。
- **像素级细化有效**：LPOSS+比LPOSS平均提升0.8% mIoU，Boundary IoU提升1.8%，尤其在边界区域效果显著。
- **跨窗口联合预测的优势**：当采用小窗口（224×224）时，LPOSS+表现最佳（因保留训练分辨率），而其他方法因窗口上下文不足性能下降；集成两个尺度进一步改善。
- **标签传播优于简单亲和矩阵平滑**：LPOSS的geodesic相似性比CLIP-DINOiser的Euclidean亲和矩阵更有效。
- **Oracle实验揭示块级上限**：即使是完美块级预测，仅靠上采样也会损失约15% mIoU和30% Boundary IoU，说明像素级处理必不可少。

### 7. 优点
1. **训练-free**：无需任何微调或额外训练，直接利用预训练模型，计算成本低、易部署。
2. **理论优雅**：标签传播有清晰的优化目标（二次代价），并能解析为线性系统，可高效求解。
3. **解耦设计**：特征提取与预测分离，允许使用最佳窗口大小提取特征，同时进行全图联合预测，兼顾局部特征质量与全局上下文。
4. **像素级细化**：突破块级分辨率瓶颈，显著提升边界分割质量（Boundary IoU增量大）。
5. **通用性**：LPOSS+可作后处理用于其他分割方法（如DINOv2线性头），有一定泛化能力。
6. **无数据集特定调参**：所有超参数跨数据集固定，表明方法鲁棒。

### 8. 不足与局限
- **对特定数据集性能非最优**：在VOC20和Object数据集上，LPOSS+的mIoU低于ProxyCLIP，作者归因于窗口大小选择及ProxyCLIP使用了数据集特定的背景过滤策略。若未针对每个数据集优化，可能无法始终最优。
- **依赖特征质量**：VM（DINO）的补丁特征对图构建至关重要，若VM本身质量差或场景特殊（如极低光照），效果可能下降。
- **计算成本未量化**：尽管无需训练，但构建大图（所有窗口所有patch）并求解线性系统仍需一定GPU内存和时间，尤其在高分辨率图像上。论文未报告推理速度。
- **像素级细化引入额外计算**：对全图每个像素建图（即便用Lab颜色空间和局部邻域），当图像尺寸大时（如Cityscapes 2K），r=13邻域导致图规模大，可能较慢。
- **无理论分析或大规模验证**：缺少对标签传播收敛性、数值稳定性以及对极不平衡类别影响的讨论。实验限于中低分辨率（短边448），未在高分辨率（如4K）上测试。
- **未与训练-based方法对比**：虽然定位是训练-free方法，但若与最近训练-based方法（如FC-CLIP）比较，差距可能较大，限制了全面理解。

### 9. 创新点与贡献
- **提出无训练优化框架**：首次将经典标签传播算法系统性地应用于开放词汇分割的后处理，克服了VLM块级特征内模态相似性不足的问题，且无需任何微调或重新训练。
- **双层级联细化策略**：从块级标签传播（LPOSS）到像素级标签传播（LPOSS+），由粗到精逐步提升分割分辨率与边界精度，突破了ViT块级分辨率上限。
- **跨窗口联合推理机制**：特征提取与预测解耦，允许保留预训练分辨率进行特征提取，同时利用全图patch构建图实现全局一致预测，避免了滑动窗口独立预测导致的不连续性。
- **多模态特征融合的巧妙使用**：利用视觉模型（DINO）较强的内模态块间关系作为图边的外观相似性，互补VLM弱化的块间关系，同时保留VLM的跨模态分类能力。

### 10. 未来工作方向
- **动态窗口策略**：根据图像内容自动调整窗口大小和步长，进一步平衡局部细节与全局上下文，避免固定窗口带来的边界伪影。
- **更高效的标签传播求解**：探索近似求解或自适应稀疏化策略，减少高分辨率图像上的内存与时间开销。
- **扩展至视频或点云**：将标签传播的时空连续性应用于视频语义分割或3D点云分割，利用帧间或点间相似性进行传播。
- **结合训练-based方法**：将LPOSS+作为轻量级后处理模块插入训练-based分割管线，验证其对预训练模型边界精度的提升效果。
- **理论分析**：研究标签传播对类别不平衡、小目标、遮挡场景的敏感性，并提供收敛保证。

### 11. 综合评价
LPOSS是一项扎实且实用的无训练后处理方法，有效弥补了开放词汇分割中VLM块级预测的固有缺陷。其核心贡献在于将标签传播这一经典工具重新引入现代视觉-语言模型的下游任务，并巧妙地结合了视觉模型与语言模型的优势。实验设计全面、公平，消融实验清晰验证了各模块的必要性。虽然在某些特定数据集上略逊于专门优化方法，但整体性能提升显著，尤其在边界质量上具有明显优势。该方法无需训练、参数固定，非常适合实际部署和作为通用后处理工具。未来若能在计算效率与理论深度上进一步突破，有望成为开放词汇分割领域的标准基线。

（完）
