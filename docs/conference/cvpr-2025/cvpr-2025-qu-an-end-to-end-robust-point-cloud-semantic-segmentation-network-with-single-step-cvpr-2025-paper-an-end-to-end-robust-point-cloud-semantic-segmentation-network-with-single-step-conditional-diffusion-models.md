---
title: An End-to-End Robust Point Cloud Semantic Segmentation Network with Single-Step Conditional Diffusion Models
title_zh: 基于单步条件扩散模型的端到端鲁棒点云语义分割网络
authors: "Qu, Wentao, Wang, Jing, Gong, YongShun, Huang, Xiaoshui, Xiao, Liang"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Qu_An_End-to-End_Robust_Point_Cloud_Semantic_Segmentation_Network_with_Single-Step_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 6.0
evidence: 基于扩散模型的鲁棒点云语义分割
tldr: 现有条件扩散模型在3D语义分割中难以拟合几何细节。CDSegNet提出条件-噪声框架，将噪声网络建模为可学习部分，实现单步分割。在多个点云数据集上达到鲁棒且高效的分割效果。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 881, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 879, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 877, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1816, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1810, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1822, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 878, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 873, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 872, \"height\": 362, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1798, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 524, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 597, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 870, \"height\": 119, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 868, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-qu-an-end-to-end-robust-point-cloud-semantic-segmentation-network-with-single-step-cvpr-2025-paper/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 869, \"height\": 194, \"label\": \"Table\"}]"
motivation: 扩散模型处理3D场景几何细节困难且训练推理慢。
method: 设计条件-噪声框架（CDSegNet），将噪声网络作为可学习模块。
result: 在点云分割任务上达到鲁棒性能且推理更快。
conclusion: 重新设计扩散框架可提升3D语义分割的效率与精度。
---

## Abstract
Existing conditional Denoising Diffusion Probabilistic Models (DDPMs) with a Noise-Conditional Framework (NCF) remain challenging for 3D scene understanding tasks, as the complex geometric details in scenes increase the difficulty of fitting the gradients of the data distribution (the scores) from semantic labels. This also results in longer training and inference time for DDPMs compared to non-DDPMs. From a different perspective, we delve deeply into the model paradigm dominated by the Conditional Network. In this paper, we propose an end-to-end robust semantic Segmentation Network based on a Conditional-Noise Framework (CNF) of DDPMs, named CDSegNet. Specifically, CDSegNet models the Noise Network (NN) as a learnable noise-feature generator. This enables the Conditional Network (CN) to understand 3D scene semantics under multi-level feature perturbations, enhancing the generalization in unseen scenes. Meanwhile, benefiting from the noise system of DDPMs, CDSegNet exhibits strong robustness for data noise and sparsity in experiments. Moreover, thanks to CNF, CDSegNet can generate the semantic labels in a single-step inference like non-DDPMs, due to avoiding directly fitting the scores from semantic labels in the dominant network of CDSegNet. On public indoor and outdoor benchmarks, CDSegNet significantly outperforms existing methods, achieving state-of-the-art performance.

---

## 论文详细总结（自动生成）

好的，我将根据您提供的论文内容，生成一段符合要求的结构化中文总结。

# 论文总结：An End-to-End Robust Point Cloud Semantic Segmentation Network with Single-Step Conditional Diffusion Models

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：点云语义分割在自动驾驶、机器人等实时应用中至关重要，但现有基于深度学习的点云分割方法对真实世界中点云存在的噪声和稀疏性敏感，鲁棒性不足。另一方面，条件扩散模型（DDPMs）因其固有的噪声鲁棒性而受到关注，但其经典的噪声条件框架（NCF）在处理复杂的3D场景几何细节时，难以从语义标签中拟合数据分布的梯度（得分），导致训练和推理需要大量迭代步数（通常数十到上千步），无法满足实时性要求。
- **整体含义**：论文旨在解决DDPMs在3D语义分割中“鲁棒性强但效率低”的困境，提出了一种新的条件-噪声框架（CNF），在保留DDPM鲁棒性的同时实现单步推理，从而在分割性能和推理速度之间取得更好平衡。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：重新设计DDPM框架，将主导地位从噪声网络（NN）转移到条件网络（CN）。在CNF中，NN被降级为轻量级、可学习的噪声特征生成器，为CN提供多级特征扰动，增强其泛化能力；而CN作为主导网络，专注于从点云中直接学习语义分割。这样，模型在训练时保留了DDPM的噪声添加模式（从而继承噪声和稀疏鲁棒性），但在推理时类似非扩散模型，仅需单步输出。
- **关键技术细节**：
    1. **条件-噪声框架（CNF）**：
        - 训练目标分为两部分：
            - NN训练：保持DDPM的噪声拟合目标，即预测添加的噪声 $\epsilon$：$L(\theta) = \mathbb{E}_{\epsilon \sim \mathcal{N}(0,I)} || \epsilon - \epsilon_\theta(c_t, t) ||^2$，其中 $c_t$ 是加噪后的点云，$t$ 是时间步。
            - CN训练：通过特征融合模块（FFM）接收NN的扰动特征，学习语义分割：$L(\psi) = \ell_{task}(x_0, f_\psi(f_t(c), c))$，其中 $f_t(c)$ 是经过FFM过滤后的噪声特征。
        - 整个模型使用几何损失策略（GLS）进行多任务优化：$L_{total} = \sqrt{L(\theta) \cdot L(\psi)}$，平衡两个分支的收敛速度。
    2. **网络架构（CDSegNet）**：
        - **辅助噪声网络（NN）**：采用轻量级Transformer-U-Net，仅以时间步 $t$ 为条件，生成多尺度噪声特征。
        - **特征融合模块（FFM）**：位于NN和CN之间的瓶颈层，使用交叉注意力机制（Cross-Attention）将NN的噪声特征单向传递给CN，自适应地过滤合理扰动，防止过度噪声损害分割性能。
        - **主导条件网络（CN）**：采用与NN类似但更深（四阶段编解码）的Transformer-U-Net结构，直接输入原始点云，结合FFM输出的扰动特征，输出语义分割结果。
    3. **单步推理**：推理时，NN输入随机噪声 $c_T \sim \mathcal{N}(0,I)$ 和时间步 $T=1000$，产生特征后经FFM传入CN，CN直接输出预测标签，无需迭代去噪过程。
- **公式**：主要损失函数（式7、8、11）如上所述。

## 3. 实验设计：数据集、基准、对比方法
- **数据集**：
    - **室内**：ScanNet（1201训练/312验证/100测试）、ScanNet200（更细粒度200类，划分相同）。
    - **室外**：nuScenes（700训练/150验证/150测试）。
    - 点云分别体素化为0.02m、0.02m、0.05m。
- **基准**：论文自定义一个“Baseline”，即去除CDSegNet中NN的扩散建模部分，将其转换为一个近似输入的轻量级CN（使用MSE损失）。
- **对比方法**：
    - **室内**：PTv1, MinkUNet, ST, OctFormer, PTv2, PTv3等。
    - **室外**：RangeNet53++, PolarNet, SalsaNext, AMVNet, Cylinder3D, PVKD, RPVNet, SphereFormer, PTv3等。
    - 还对比了引入CNF到MinkUNet和PTv3后的变体（MinkUNet+CNF, PTv3+CNF）。
- **评价指标**：mIoU, mAcc, allAcc。

## 4. 资源与算力
- 论文中未明确说明训练所使用的GPU型号、数量或具体训练时长。仅在表4脚注中提到推理时间（IT）和内存（MM）是在单张NVIDIA 3090 GPU上、batch size=1、不使用测试时增强（TTA）和分片推理的情况下测量的。可推断模型训练也在类似环境下进行，但具体算力细节缺失。

## 5. 实验数量与充分性
- **实验数量**：充分且全面，主要包括：
    1. **主表结果**：ScanNet (Tab.1)、ScanNet200 (Tab.1)、nuScenes (Tab.2) 上的语义分割性能对比，涵盖多个SOTA方法。
    2. **鲁棒性实验**：
        - 噪声鲁棒性：施加不同强度（τ=0.01~1.0）的Gaussian、Uniform、Laplace、Poisson噪声，对比PTv2、PTv3和CDSegNet（Tab.3, Fig.7）。
        - 稀疏鲁棒性：在ScanNet上随机采样5%~50%训练/验证数据进行训练，测试全量验证集（Fig.8）。
    3. **泛化能力**：
        - 将CNF应用到其他主干（MinkUNet, PTv3）在三个数据集上的表现（Tab.4）。
        - nuScenes测试集结果对比（Tab.5）。
        - 引入CNF到点云分类任务（PointNet, PointNet++）在ModelNet40上的结果（Tab.6）。
    4. **消融实验**：
        - 扩散建模的必要性（Tab.7）：去除NN（Ours-CN）、去除扩散建模（Baseline）与完整CDSegNet对比。
        - 噪声调度范围的影响（Fig.9b）。
        - 多任务优化策略对比：EW, RLW, UW, GLS（Tab.8）。
        - 训练损失曲线对比（Fig.9a）。
- **充分性与公平性**：实验设计较为全面，覆盖了性能、鲁棒性、泛化性和消融分析。公平性方面，基线设置合理（去除扩散建模但保持参数量），对比方法均为近年公开的SOTA，但未提及超参数调优细节和多次重复实验的方差。此外，部分对比（如PTv3+PPT使用了额外训练数据或多数据集联合训练）被明确指出，比较透明。

## 6. 主要结论与发现
- CDSegNet在室内外三个大型基准（ScanNet、ScanNet200、nuScenes）上均取得了显著优于现有方法的性能，尤其在mIoU指标上达到SOTA。
- CDSegNet表现出对数据噪声（尤其是高斯噪声和拉普拉斯噪声，即接近扩散模型建模分布的噪声）和点云稀疏性的强鲁棒性，并且在欠采样数据和较少训练数据下表现更佳。
- CNF框架成功保留了DDPM的鲁棒性优势，同时避免了多步迭代的缺点，实现了单步推理，效率与普通非扩散模型相当。
- 噪声拟合（而非目标值拟合）是DDPM噪声鲁棒性的主要来源；多级扰动特征增强了CN的泛化能力，缓解了过拟合。

## 7. 优点：方法与实验设计的亮点
- **方法创新**：提出的CNF框架巧妙地反转了DDPM中NN和CN的角色，在保持DDPM核心噪声系统优势的同时，突破了迭代步数瓶颈，据作者称是首个将DDPM端到端引入点云语义分割的工作。
- **效率提升**：单步推理极大地降低了推理延迟，满足了自动驾驶等实时应用的需求。
- **鲁棒性全面验证**：不仅测试了标准噪声，还覆盖了多种分布噪声（Uniform、Laplace、Poisson）和稀疏场景，实验充分且有说服力。
- **泛化性验证**：将CNF应用于其他主干网络（MinkUNet, PTv3）和其他任务（分类）均取得提升，证明了框架的通用性。
- **消融实验系统**：通过去除扩散建模、对比不同损失策略、分析噪声调度范围等，清晰地展示了各组件的作用。

## 8. 不足与局限
- **算力资源未明确**：论文未报告训练所需的GPU型号、数量和训练时间，难以复现和评估训练成本。
- **实验方差缺失**：未提供多次运行的性能均值和标准差，结果可能受随机性影响。
- **室外场景对比有限**：nuScenes上对比的方法多为较早的SOTA（如SphereFormer, Cylinder3D），较新的方法（如PTv3）参数量更大但性能仍低于CDSegNet，但所提变体PTv3+CNF也未能超越CDSegNet，可能暗示CDSegNet的参数量优势（101.4M）带来了不公平对比。论文也指出CDSegNet参数量大，但通过CNF有效避免了过拟合。
- **鲁棒性分析深度不足**：对噪声鲁棒性的来源解释（噪声拟合）仅为推测，作者表示“希望在未来验证”，缺乏严格的理论证明或控制实验。
- **方法局限性**：CNF需要同时训练NN和CN两个分支，训练阶段仍需遵循扩散模型的多步噪声策略（虽然推理简化），且FFM的交叉注意力可能增加计算量。对于极高实时性要求（如毫秒级）的场景，单步推理虽好，但模型参数量（101.4M）仍可能成为瓶颈。
- **论文未讨论模型在极端稀疏或高度动态场景下的表现**（如点云缺失严重或目标快速运动）。

（完）
