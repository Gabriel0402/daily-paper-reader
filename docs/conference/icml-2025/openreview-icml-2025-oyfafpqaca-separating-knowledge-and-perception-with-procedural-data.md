---
title: Separating Knowledge and Perception with Procedural Data
title_zh: 用程序化数据分离知识与感知
authors: "Adrian Rodriguez-Munoz, Manel Baradad, Phillip Isola, Antonio Torralba"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oyFAFpqaca"
tags: ["query:mmseg"]
score: 7.0
evidence: 使用程序化数据训练表示模型，零样本语义分割性能接近真实数据训练的模型
tldr: "该工作探索仅使用程序化数据训练视觉表示模型，通过视觉记忆实现与真实世界图像的完全隔离。模型在NIGHTS视觉相似性任务上表现优异，在细粒度分类上超越真实数据训练的模型，在COCO语义分割上零样本R²与真实数据模型差距在10%以内。该方法展示了程序化数据作为隐私保护型视觉基础模型的潜力。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1779, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 863, \"height\": 221, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 1451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1774, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 863, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1706, \"height\": 1585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1781, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 871, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1773, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 866, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1777, \"height\": 1938, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1601, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyfafpqaca/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1597, \"height\": 1225, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oyfafpqaca/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 864, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyfafpqaca/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 624, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyfafpqaca/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 505, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyfafpqaca/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 799, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyfafpqaca/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 787, \"height\": 430, \"label\": \"Table\"}]"
motivation: 现有视觉模型依赖真实数据训练，存在隐私风险且知识难以与感知分离。
method: 提出仅用程序化数据训练表示模型，并利用视觉记忆数据库直接执行下游任务无需微调。
result: "在NIGHTS、CUB200、Flowers102和ImageNet-1K上达到或接近真实数据训练模型的性能，COCO零样本分割R²差距小于10%。"
conclusion: 程序化数据训练足以获得高性能视觉表示，同时实现与真实场景的完全隔离，具备隐私优势。
---

## Abstract
We train representation models with procedural data only, and apply them on visual similarity, classification, and semantic segmentation tasks without further training by using visual memory---an explicit database of reference image embeddings. Unlike prior work on visual memory, our approach achieves full compartmentalization with respect to all real-world images while retaining strong performance. Compared to a model trained on Places, our procedural model performs within 1\% on NIGHTS visual similarity, outperforms by 8\% and 15\% on CUB200 and Flowers102 fine-grained classification, and is within 10\% on  ImageNet-1K classification. It also demonstrates strong zero-shot segmentation, achieving an $R^2$ on COCO within 10\% of the models trained on real data. Finally, we analyze procedural versus real data models, showing that parts of the same object have dissimilar representations in procedural models, resulting in incorrect searches in memory and explaining the remaining performance gap.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 论文的核心问题与整体含义
- **研究动机**：现代视觉模型通过梯度下降在真实图像上训练，存在隐私泄露、偏差风险以及难以高效增删数据（数据遗忘）的问题。权重存储的知识“黑箱化”导致解释性差，数据遗忘需重训练或微调。
- **核心思想**：提出将“知识如何表示”（特征嵌入）与“知识存储什么”（视觉记忆）显式分离。通过仅使用程序化数据（非真实、由代码生成的抽象图像）训练嵌入模型，将全部真实数据隔离到视觉记忆数据库中，从而实现对真实数据的完美控制——增删数据仅需修改数据库，无需重新训练嵌入模型。
- **整体含义**：该框架可在几乎不牺牲性能的前提下，提供高效的数据遗忘、隐私保证和可控性，尤其适用于隐私敏感场景（如医疗、人脸数据）。

## 2. 方法论
- **核心思想**：
  - 使用程序化数据（如OpenGL生成的抽象形状和纹理）训练视觉Transformer（ViT），采用自监督学习目标DINO（local-to-global similarity）。
  - 训练后，嵌入模型提取的向量直接用于下游任务：对查询图像提取嵌入，在视觉记忆数据库中进行k近邻（KNN）搜索，以多数投票或最近邻标签作为输出（分类/分割）。
- **关键技术细节**：
  - **新的程序化数据生成过程**：提出“Shaders KML”和“Shaders KML Mixup”。Shaders KML通过K-Means在RGB空间中从着色器图像提取混合掩码，增加多样性；再在Shaders KML基础上应用Mixup以抑制捷径解，形成Shaders KML Mixup。
  - **视觉记忆机制**：分类/分割时无需额外训练，通过KNN在内存数据库中检索。添加/删除数据只需操作数据库条目，无需重训练嵌入模型。
  - **隐私与遗忘分析**：嵌入仅基于非真实程序化数据，因此真实数据不参与嵌入训练，仅作为内存。删除真实数据样本只需从内存中移除，且可轻松验证差分隐私：比较模型在有/无某样本时的预测是否变化。
- **算法流程**（文字说明）：
  1. 生成程序化数据（如Shaders KML Mixup）。
  2. 使用DINO自监督学习训练ViT嵌入模型（仅使用程序化数据）。
  3. 对于给定真实图像任务（分类/分割），将全部真实图像（训练集或参考图像）通过嵌入模型提取特征存入内存数据库。
  4. 对于新查询图像，提取嵌入，在内存中执行KNN搜索，输出多数标签或最近邻标签。

## 3. 实验设计
- **使用的数据集与场景**：
  - **视觉相似性**：NIGHTS（人类视觉相似性2AFC基准）。
  - **细粒度分类**：CUB200（鸟类）、Flowers102（花卉）、Food101。
  - **通用图像分类**：ImageNet-1K。
  - **语义分割**：COCO（零样本PCA分割）、Ade20k（上下文分割）、Pascal（KNN分割）。
  - **医学图像分类**：MedMNIST（10个数据集）。
  - **人脸识别**：CelebA。
- **Benchmark**：对比方法包括：
  - 真实数据训练模型：ImageNet（有领域重叠）、Places（无领域重叠）。
  - 先前的程序化数据方法：StyleGAN、Shaders、Shaders Mixup（Baradad et al., 2022）。
  - 白盒基线：随机初始化、SIFT、RGB。
- **实验设计特点**：
  - 所有模型使用相同的DINO超参数（来源于ImageNet最优设置），未为程序化数据专门调参，确保公平。
  - 对比了KNN分类与线性解码（见附录），分析了性能差距来源（如程序化模型对同一物体不同部分表示不一致）。
  - 包含准确的统计检验（z-test）和标准差报告。

## 4. 资源与算力
- 文中明确提及训练线性分类器需4 GPU天（8-V100节点），而计算KNN分类所需嵌入仅需1.5 GPU小时（单GPU）。训练嵌入模型本身（ViT-Small）使用与原始DINO相同的设置：100 epoch，batch size 512，学习率1e-3，AdamW。
- 未单独报告训练程序化嵌入模型的具体GPU时长，但可推断约为数天级别。文中未提供具体型号（V100/H100等）但提及V100 MSRP约10,000 USD。

## 5. 实验数量与充分性
- **主要实验组数**：包括6类任务（相似性、3个细粒度分类、ImageNet-1K、3种分割、10个医学数据集、人脸检索），对比超过7个方法（ImageNet, Places, 多种程序化数据, 随机初始化, 白盒SIFT/RGB）。
- **消融分析**：对比了不同程序化数据变体（Shaders, Shaders Mixup, Shaders KML, Shaders KML Mixup, StyleGAN）的性能，分析Mixup和KML的互补作用。
- **扩展实验**：模型大小缩放实验（ViT-Small到大型），线性解码GradCam，硬标签K-Means分割定性，差分隐私分析。
- **充分性评估**：实验覆盖多种任务，且进行了统计显著性检验（z-test），评价标准客观（Top-1准确率、R²、NIGHTS分数）。但程序化模型仅限于较小型ViT-Small，未充分探索更大模型（仅简要提及缩放趋势）。此外，未在真实世界增量学习场景中测试遗忘效率。

## 6. 主要结论与发现
1. 仅用程序化数据训练的嵌入模型配合视觉记忆，可在NIGHTS视觉相似性上达到接近Places模型的性能（差距<1%），在细粒度分类上甚至超越Places（CUB200高15%，Flowers102高8%），在ImageNet-1K上差距约10%。
2. 程序化模型具备零样本语义分割能力，COCO的R²与真实数据模型差距<10%，且能进行上下文分割。
3. 程序化模型的主要局限：由于未见过真实物体，对同一物体不同部分的表示可能高度不一致（如自行车车轮中心与辐条），导致KNN搜索时错配同类物体不同部分，造成分类错误。
4. 在隐私方面，仅0.6%的ImageNet训练样本被标记为“非私有”（移除后影响测试集预测），表明模型高度“健忘”，但准确率与隐私率呈线性关系。
5. 模型不随规模扩大而过拟合，更大模型可带来更高性能。

## 7. 优点
- **创新性**：首次将程序化数据训练与视觉记忆框架深度结合，实现真实数据与嵌入训练完全隔离，解决了之前视觉记忆方法中嵌入仍基于真实数据的问题。
- **实用价值**：提供高效数据遗忘机制（仅需编辑数据库），适用于需要遵守隐私法规（如GDPR）的场景；在医学图像分类上7/10数据集超越原始论文最佳结果（使用ResNet全监督）。
- **实验设计严谨**：统一超参数，避免为程序化数据特殊优化；进行统计检验；对比多个基线（包括白盒方法与随机初始）。
- **透明度**：详细分析了程序化模型性能差距的根源（局部视觉特征对齐不良），给出直观特征PCA可视化。

## 8. 不足与局限
- **性能差距**：在ImageNet-1K上仍比Places模型低10%，在Pascal KNN分割任务中表现差（由于物体部分表示不一致）。
- **实验覆盖有限**：仅使用ViT-Small架构，未验证更大模型能否完全弥合差距；仅测试了DINO自监督方法，未探索其他SSL（如SimCLR, MAE）。
- **遗忘评估简化**：仅分析了差分隐私中“非私有样本”的比例，未测试大规模数据删除的实际运行时间或能耗。
- **应用限制**：程序化数据生成需要手工设计（OpenGL代码），不同程序化过程性能差异大（如StyleGAN远低于Shaders变体）；当前最佳过程Shaders KML Mixup仍依赖大量人工工程。
- **风险与偏差**：尽管程序化数据避免真实世界语义，但抽象形状仍可能无意中引入几何/纹理偏差（如偏向特定颜色或空间频率），未做系统性偏差分析。

（完）
