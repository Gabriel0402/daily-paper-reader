---
title: Repurposing Stable Diffusion Attention for Training-Free Unsupervised Interactive Segmentation
title_zh: 重新利用稳定扩散注意力实现免训练无监督交互式分割
authors: "Karmann, Markus, Urfalioglu, Onay"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Karmann_Repurposing_Stable_Diffusion_Attention_for_Training-Free_Unsupervised_Interactive_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 4.0
evidence: 利用扩散注意力进行交互式分割
tldr: 本文提出一种无需训练的无监督交互式分割方法，利用Stable Diffusion的自注意力机制，将其解释为马尔可夫转移算子，通过迭代计数得到分割图。该方法避免了传统方法对标注数据的依赖，为交互式分割提供了新的思路。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1808, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1803, \"height\": 905, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1806, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1816, \"height\": 567, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 824, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 720, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-karmann-repurposing-stable-diffusion-attention-for-training-free-unsupervised-interactive-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1812, \"height\": 1252, \"label\": \"Table\"}]"
motivation: 现有无监督交互式分割依赖自监督预训练模型生成伪标签，本文探索直接利用预训练扩散模型的自注意力进行分割。
method: 将Stable Diffusion的自注意力张量解释为马尔可夫转移算子，通过迭代马尔可夫链计算像素达到概率阈值的步数，生成马尔可夫迭代图。
result: 在多个数据集上验证了该方法无需训练即可实现有效的交互式分割。
conclusion: 表明扩散模型的自注意力可被重新用于交互式分割任务，无需额外训练。
---

## Abstract
Recent progress in interactive point prompt based Image Segmentation allows to significantly reduce the manual effort to obtain high quality semantic labels. State-of-the-art unsupervised methods use self-supervised pre-trained models to obtain pseudo-labels which are used in training a prompt-based segmentation model. In this paper, we propose a novel unsupervised and training-free approach based solely on the self-attention of Stable Diffusion. We interpret the self-attention tensor as a Markov transition operator, which enables us to iteratively construct a Markov chain. Pixel-wise counting of the required number of iterations along the Markov chain to reach a relative probability threshold yields a Markov-iteration-map, which we simply call a Markov-map. Compared to the raw attention maps, we show that our proposed Markov-map has less noise, sharper semantic boundaries and more uniform values within semantically similar regions. We integrate the Markov-map in a simple yet effective truncated nearest neighbor framework to obtain interactive point prompt based segmentation. Despite being training-free, we experimentally show that our approach yields excellent results in terms of Number of Clicks (NoC), even outperforming state-of-the-art training based unsupervised methods in most of the datasets. Code is available at https://github.com/mkarmann/m2n2.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
交互式点提示图像分割旨在通过少量用户点击获得高质量语义分割。现有无监督方法依赖自监督预训练模型（如DINO、MAE）生成伪标签，再训练分割模型，过程复杂且需要额外训练。本文探索直接利用预训练扩散模型（Stable Diffusion 2）的自注意力机制，无需任何训练即可实现交互式分割，从而降低对标注数据和计算资源的依赖。

## 2. 方法论

### 核心思想
将Stable Diffusion 2的自注意力张量解释为马尔可夫转移算子，通过迭代马尔可夫链计算每个像素达到相对概率阈值所需的步数，生成“马尔可夫图”（Markov-map）。该图具有更少噪声、更清晰语义边界和更均匀的区域值。

### 关键技术细节
- **注意力聚合**：对输入图像执行单步去噪，提取U-Net中最高分辨率（128×128）的每个Transformer块自注意力，按权重平均聚合为张量A ∈ R^(h×w×h×w)。
- **马尔可夫链构建**：将A展平为右随机矩阵，作为转移矩阵。对每个提示点用one-hot初始化状态p0，迭代pt = p0·A^t。通过迭代比例拟合（IPF）将A转换为双随机矩阵，确保所有起始状态最终收敛到均匀分布。
- **马尔可夫图计算**：定义m[k] = min{t | pt[k]/max(pt) > τ}，其中τ为相对概率阈值。对连续时间帧线性插值，并利用联合双边上采样（JBU）放大至原图分辨率，得到马尔可夫图M。
- **洪泛填充（Flood Fill）**：为支持实例分割，对单个提示点的马尔可夫图执行修正洪泛填充，抑制局部最小值，确保全局最小值为提示点处。
- **截断最近邻（Truncated Nearest Neighbor）**：距离函数d(xi, xq) = Mi[xq] / λi，其中λi为自适应阈值。通过最大化四个得分函数（先验、边缘、正点一致性、负点一致性）的乘积确定λi。最终分割由最近邻且距离≤1的类决定。

### 算法流程
1. 输入图像和提示点集合。
2. 运行SD2单步去噪，提取注意力张量并聚合。
3. 对每个提示点生成马尔可夫图（含洪泛填充）。
4. 自适应计算每个提示点的λi。
5. 应用截断最近邻，输出每个像素的分割标签。

## 3. 实验设计

### 数据集
- **GrabCut**：50张图像，50个实例。
- **Berkeley**：96张图像，100个实例（部分与GrabCut重叠）。
- **SBD**：2857张图像，6671个实例（验证集）。
- **DAVIS**：345张图像，345个实例（高质量视频对象分割）。

### 评估指标
- **NoC85**：达到IoU=85%所需的平均点击次数。
- **NoC90**：达到IoU=90%所需的平均点击次数。模拟用户交互，每次点击放置在最大误差区域中心，最大点击20次。

### 对比方法
- **监督方法**：SimpleClick (ViT-B/H)、CPlot、CFR-ICL、FocalClick、InterFormer、OIS（均在SBD训练集或COCO+LVIS上训练）。
- **无监督方法（基于伪标签训练）**：TokenCut、FreeMask、DSM、MIS（使用伪标签训练SimpleClick模型）。
- **无监督免训练方法**：GraphCut、Random Walk、Geodesic Matting、GSC、ESC，以及作者提供的基线Attention-NN和KL-NN（均基于SD2）。

## 4. 资源与算力
论文未明确说明训练所需算力（因为方法是免训练的）。仅提及了推理性能：在RTX 4090上，当图像分辨率为854×480时，缓存注意力张量和马尔可夫图后，平均每点击0.6秒。未报告模型训练（SD2本身预训练）的算力需求。

## 5. 实验数量与充分性
- **主实验**：在4个数据集上与15种以上方法全面对比（表3），涵盖监督、无监督（训练和免训练）方法。
- **消融实验**：
  - 注意力块权重（表1）：评估不同层聚合效果。
  - 阈值得分函数（表2）：评估先验、边缘、正/负一致性的贡献。
  - 超参数影响（图4）：考察时间步、注意力分辨率、温度T、马尔可夫阈值τ对NoC的影响。
  - 不同骨干网络（表3）：SD2、SD1.1、ViT-B。
  - 马尔可夫图变体：有无洪泛填充。
- **定性结果**：图3比较语义图，图5展示DAVIS各难度案例。
- 实验设计客观：遵循前人评估协议，使用相同数据集和模拟交互策略。未进行跨域（如医学）的广泛测试，但报告了在BraTS和OAIZIB上的初步结果（IoU低于SimpleClick）。

## 6. 主要结论与发现
- 提出的马尔可夫图相比原始注意力图噪声更低、边界更清晰、语义区域更均匀。
- 所提框架M2N2（无需训练）在三个数据集（GrabCut、Berkeley、DAVIS）上超越所有无监督训练方法（如MIS），在SBD上仅次于MIS（MIS在SBD训练集上训练过）。
- 在DAVIS上NoC85降低1.73，NoC90降低1.72，显著提升。
- SD2（最高注意力分辨率128×128）优于SD1.1和ViT-B。
- 存在领域偏差：在医学图像（BraTS、OAIZIB）上性能下降。

## 7. 优点
- **首次提出免训练无监督点提示交互式分割**：仅利用预训练扩散模型的自注意力，无需任何伪标签生成或下游训练。
- **方法创新性**：将注意力张量解释为马尔可夫转移算子，提出马尔可夫图，有效提升语义特征质量。
- **简单有效**：洪泛填充和自适应阈值设计巧妙，无需额外监督。
- **计算高效**：推理速度快（0.6秒/点击），适合交互式应用。
- **实验全面**：多数据集、多基线、多消融，验证了各组件有效性。

## 8. 不足与局限
- **领域偏差**：对医学图像等自然图像以外的领域泛化能力弱，可能受SD2预训练数据分布影响。
- **细粒度局限**：由于注意力分辨率低（128×128），处理细长或小结构（如网球拍、薄枝）时需要较多点击。
- **重叠实例分割**：单个提示点的马尔可夫图无法分离语义相似或重叠的实例，需多提示点辅助。
- **洪泛填充限制**：不能处理遮挡导致的分割碎片（如被遮挡的犀牛需两个点）。
- **实验覆盖不足**：未在更多领域（如遥感、街景）测试；也未与最新免训练扩散方法（如PaintSeg）在同等条件下对比（但PaintSeg不支持多点交互）。
- **资源报告不完整**：未提及SD2预训练成本，仅给出推理速度。

（完）
