---
title: Multi-Label Prototype Visual Spatial Search for Weakly Supervised Semantic Segmentation
title_zh: 用于弱监督语义分割的多标签原型视觉空间搜索
authors: "Duan, Songsong, Yang, Xi, Wang, Nannan"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Duan_Multi-Label_Prototype_Visual_Spatial_Search_for_Weakly_Supervised_Semantic_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 6.0
evidence: 基于多标签原型搜索的弱监督语义分割
tldr: 弱监督语义分割中CAM和自注意力图常导致分割不完整。MuP-VSS提出多标签原型视觉空间搜索，通过可学习类令牌查询图像块令牌，并结合原型优化。在PASCAL VOC等数据集上取得了优于主流方法的性能。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 903, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 867, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1750, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1699, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 870, \"height\": 421, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 874, \"height\": 917, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 873, \"height\": 970, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 840, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-duan-multi-label-prototype-visual-spatial-search-for-weakly-supervised-semantic-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 827, \"height\": 311, \"label\": \"Table\"}]"
motivation: CAM和自注意力图因分类偏差导致分割不完整。
method: 可学习类令牌作为查询，搜索相似视觉令牌，并优化多标签原型。
result: 在弱监督分割基准上达到新高度。
conclusion: 原型搜索可有效缓解分类偏差带来的分割不完整问题。
---

## Abstract
Existing Weakly Supervised Semantic Segmentation (WSSS) relies on the CNN-based Class Activation Map (CAM) and Transformer-based self-attention map to generate class-specific masks for semantic segmentation. However, CAM and self-attention maps usually cause incomplete segmentation due to classification bias issue. To address this issue, we propose a Multi-Label Prototype Visual Spatial Search (MuP-VSS) method with a spatial query mechanism, which learns a set of learnable class token vectors as queries to search the similarity visual tokens from image patch tokens. Specifically, MuP-VSS consists of two key components: multi-label prototype representation and multi-label prototype optimization. The former designs a global embedding to learn the global tokens from the images, and then proposes a Prototype Embedding Module (PEM) to interact with patch tokens to understand the local semantic information. The latter utilizes the exclusivity and consistency principles of the multi-label prototypes to design three prototype losses to optimize them, which contain cross-class prototype (CCP) contrastive loss, cross-image prototype (CIP) contrastive loss, and patch-to-prototype (P2P) consistency loss. CCP loss models exclusivity of multi-label prototypes learned from a single image to enhance the discriminative properties of each class better. CCP loss learns the consistency of the same class-specific prototypes extracted from multiple images to enhance the semantic consistency. P2P loss is proposed to control the semantic response of the prototype to the image patches. Experimental results on Pascal VOC 2012 and MS COCO show that MuP-VSS significantly outperforms recent methods and achieves state-of-the-art performance.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：弱监督语义分割（WSSS）通常依赖 CNN 的类激活图（CAM）或 Transformer 的自注意力图来生成类特定掩码。然而，这些方法由于**分类偏差**（classification bias）——模型在分类任务中倾向于关注最具判别性的区域——导致分割结果不完整，往往只激活物体最显著的部分。
- **研究动机**：为了克服分类偏差，作者提出将 WSSS 任务转化为**嵌入表示任务**，通过引入可学习的**多标签原型（multi-label prototypes）**作为查询向量，在视觉空间中搜索与原型相似的图像块令牌，从而生成更完整的伪像素级标签。
- **整体含义**：MuP-VSS 是一种新的弱监督范式，通过原型查询机制替代传统分类激活或自注意力图，能够生成覆盖完整物体区域的语义分割伪标签，显著提升 WSSS 性能。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：为每个类别学习一个可学习的原型向量（class-specific query token），利用这些原型与图像块令牌进行相似度匹配，获得类激活响应图（作为伪标签）。通过精心设计的表示学习和对比学习损失，优化原型表示，使其既具备类间可分性又具备类内一致性。
- **关键技术细节**：
  - **多标签原型表示（Multi-label Prototype Representation）**：
    - **全局嵌入（Global Embedding）**：将输入图像缩放到与补丁相同尺寸，通过 C 个独立的 3×3 卷积+层归一化投影函数，为每个类别生成一个全局令牌（global token）\( \mathbf{G}_i \)。
    - **原型嵌入模块（Prototype Embedding Module, PEM）**：将多标签原型 \( \mathbf{P} \) 与图像块令牌 \( \mathbf{F} \) 拼接，计算二者之间的亲和图（affinity map），并用阈值 \( \tau_{\text{PEM}} \) 过滤噪声关联，再通过 softmax 得到权重，用于交互更新原型和块令牌的特征，增强语义响应。
  - **多标签原型优化（Multi-label Prototype Optimization）**：
    - **跨类原型对比损失（CCP Loss）**：对单张图像内的不同类原型，通过余弦相似度推远彼此（增加类间可分性）。
    - **跨图像原型对比损失（CIP Loss）**：对不同图像中同一类别的原型，通过余弦相似度拉近彼此（增强类内一致性）。
    - **补丁-原型一致性损失（P2P Loss）**：计算每个块令牌与每个类原型的相似度，用阈值 \( \tau_{\text{p2p}} \) 抑制负响应，然后与多标签真实标签进行多标签分类损失，强制补丁令牌匹配前景原型、抑制背景原型。
    - 总损失：\( \mathcal{L}_{\text{total}} = \mathcal{L}_{\text{CCP}} + \mathcal{L}_{\text{CIP}} + \mathcal{L}_{\text{P2P}} + \mathcal{L}_{\text{CLS}} \)，其中 \( \mathcal{L}_{\text{CLS}} \) 是传统的多标签分类损失（施加在最后一个 ViT 层的块令牌和原型上）。
  - **推理**：直接将多标签原型 \( \mathbf{P} \) 与补丁令牌 \( \mathbf{F} \) 做点积得到类语义图 \( \mathbf{M}_p \)，再通过补丁之间的亲和图 \( \mathbf{A}_p \)（也是点积）进行空间细化得到最终语义图 \( \mathbf{M}_{\text{ref}} \)。

### 3. 实验设计
- **数据集**：
  - **Pascal VOC 2012**：训练集 10582 张，val 集 1449 张，test 集 1456 张，共 20 个前景类+1 背景类。
  - **MS COCO 2014**：训练集 82k 张，val 集 40k 张，共 80 个前景类+1 背景类。
- **Benchmark**：主流 WSSS Benchmark，使用 mean Intersection over Union (mIoU) 评估语义分割性能。种子（Seed）在训练集评估，分割模型在 val/test 集评估。
- **对比方法**：
  - CNN-based 方法：CDA, RIB, ReCAM, CLIMS, ACR, D2CAM, SFC, KTSE 等（基于 ResNet38/101）。
  - Transformer-based 方法：MCTformer, ACR+ViT, FPR, USAGE, LPCAM, PCSS, DiG, CTI 等（基于 DeiT-S 或 ViT-B）。
  - 利用视觉-语言模型的方法：CLIP-ES, DIAL, WeCLIP 等。
- **评价指标**：mIoU（%）。

### 4. 资源与算力
- **未明确说明**：论文在“Implementation Details”中只提到使用 DeiT-S 作为 backbone，Adam 优化器，学习率 5e-4，batch size 16，但未提及 GPU 型号、数量或训练时长。后处理使用了多尺度输入和密集条件随机场（DenseCRF）。文中未提供计算资源的具体信息。

### 5. 实验数量与充分性
- **实验组数**：包含多个对比表和消融实验。
  - 种子与掩码对比（表1）：在 Pascal train 集上与 14 种方法对比。
  - 语义分割性能对比（表2）：Pascal val/test 和 COCO val 上与 16 种方法对比。
  - 消融实验（表3-5）：包括组件消融（MPR、MPO 有效性）、表示模块消融（Global Embedding、PEM）、损失函数消融（CCP、CIP、P2P）。
  - 可视化定性对比（图5-7）：与 CTI、ReCAM、MCTformer 等对比。
- **充分性评判**：实验覆盖两个主流数据集，对比方法全面（包括最新 SOTA），消融实验验证了每个核心组件和损失函数的贡献，并提供了定性可视化。但缺少对不同 backbone（如更大 ViT）或不同弱监督设置（如点、框标注）的拓展实验，也未见对超参数（如阈值）的敏感性分析。整体上实验设计较充分，结论可靠。

### 6. 主要结论与发现
- MuP-VSS 在 Pascal VOC 2012 上达到：种子 71.7% mIoU（DeiT-S，训练集），掩码 74.1%；分割 val 73.6%，test 74.7%。
- 在 MS COCO 上达到 46.6% mIoU（val），优于所有仅使用图像级标签的现有方法，甚至优于结合 CLIP 的方法。
- 三个损失函数（CCP、CIP、P2P）均贡献显著，联合使用时性能提升最大（从 64.2% 提升至 71.7%）。
- 全局嵌入和原型嵌入模块（PEM）分别带来 4.0% 和 3.5% 的性能提升。
- 可视化表明 MuP-VSS 能分割出完整物体区域，克服了分类偏差导致的局部激活问题。

### 7. 优点
- **创新性**：首次将多标签原型作为查询向量用于 WSSS，将分类任务转化为嵌入表示任务，从根本上规避分类偏差。
- **方法简洁有效**：原型表示和优化无需额外复杂模块，PEM 为参数无关模块，易于集成到 ViT 中。
- **损失设计合理**：CCP 和 CIP 对比损失分别从类间和类内两个维度优化原型，P2P 损失直接约束补丁-原型响应，三损失协同效果好。
- **性能优异**：在多个 benchmark 上刷新 SOTA，特别在 COCO 这种大规模多类场景提升明显。
- **可解释性**：原型可作为类别描述符，可视化显示原型搜索得到的语义图连贯且完整。

### 8. 不足与局限
- **计算资源未公开**：论文未报告训练所需的 GPU 型号、数量及时间，不利于复现和公平比较。
- **消融不够深入**：未对阈值 \( \tau_{\text{PEM}} \) 和 \( \tau_{\text{p2p}} \) 进行灵敏度分析；未探索不同 ViT 深度（如 ViT-B/L）或更大 backbone 下的表现。
- **仅限图像级标签**：方法针对最弱的监督信号设计，未在点、涂鸦或框监督场景下验证泛化性。
- **应用限制**：依赖于 ViT 架构，可能需要修改才能适配纯 CNN 网络；原型的数量固定为类别数，对于开放长尾场景可能不灵活。
- **潜在偏差**：全局嵌入通过缩放图像并投影得到全局令牌，可能丢失小物体的细节信息；对照实验中使用的基线（如复制类令牌）可能不够强，对比优势有待更严格检验。

（完）
