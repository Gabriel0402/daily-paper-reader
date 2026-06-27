---
title: Towards Efficient Foundation Model for Zero-shot Amodal Segmentation
title_zh: 面向高效零样本amodal分割的基础模型
authors: "Liu, Zhaochen, Qiao, Limeng, Chu, Xiangxiang, Ma, Lin, Jiang, Tingting"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Liu_Towards_Efficient_Foundation_Model_for_Zero-shot_Amodal_Segmentation_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 8.0
evidence: 基于SAM的零样本amodal分割基础模型
tldr: 零样本amodal分割要求预测被遮挡物体的完整形状，现有模型效率与稳定性不足。SAMBA利用SAM的隐含先验知识，提出多级促进框架和分离-融合结构，联合学习模态与模态外特征。实验表明其在多个基准上实现高效且稳定的零样本amodal分割，拓展了SAM在开放世界中的应用。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 791, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 822, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1788, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1532, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 252, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 704, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1546, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 704, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-towards-efficient-foundation-model-for-zero-shot-amodal-segmentation-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 705, \"height\": 207, \"label\": \"Table\"}]"
motivation: 零样本amodal分割需要高效稳定的基础模型，现有SAM适配方案存在效率低和稳定性差的问题。
method: 基于SAM设计多级促进框架，采用分离-融合结构联合学习模态与模态外特征。
result: 在多个amodal分割数据集上实现领先的零样本性能，且推理速度快、结果稳定。
conclusion: SAMBA有效发掘SAM在amodal分割任务中的潜力，推动了基础模型在开放世界分割中的应用。
---

## Abstract
Aiming to predict the complete shape of partially occluded objects, amodal segmentation is an important capacity towards visual intelligence. In order to promote the practicability, zero-shot foundation model competent for the open world gains growing attention in this field. Nevertheless, prior models exhibit deficiencies in efficiency and stability. To address this problem, utilizing the implicit prior knowledge, we propose the first SAM-based amodal segmentation foundation model, SAMBA. Methodologically, a novel framework with multilevel facilitation is designed to better adapt the task characteristics and unleash the potential capabilities of SAM. In the modality level, a separation-to-fusion structure is employed that jointly learns modal and amodal segmentation to enhance mutual coordination. In the instance level, to ease the complexity of amodal feature extraction, we introduce a principal focusing mechanism to indicate objects of interest. In the pixel level, mixture-of-experts is incorporated with a specialized distribution loss, by which distinct occlusion rates correspond to different experts to improve the accuracy. Experiments are conducted on several eminent datasets, and the results show that the performance of SAMBA is superior to existing zero-shot and even supervised approaches. Furthermore, our proposed model has notable advantages in terms of speed and size.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：零样本（zero-shot）amodal分割任务——预测被遮挡物体的完整形状（含可见部分和遮挡部分）。现有模型在效率和稳定性方面存在不足。
- **背景**：实际场景中遮挡普遍存在，amodal分割对于自动驾驶、机器人抓取、图像增强等应用至关重要。传统方法大多局限于封闭世界（closed-world）设定，难以泛化到开放世界。pix2gestalt（基于扩散模型）虽实现零样本能力，但推理速度慢（约100秒/实例）、模型体积大（860M参数），且稳定性差。因此，需要构建一个**紧凑且高效**的零样本amodal分割基础模型。
- **动机**：利用SAM（Segment Anything Model）隐含的丰富先验知识（预训练于11M图像、1.1B掩码），通过参数高效微调（PEFT）将其适配到amodal分割任务，同时解决amodal任务特有的三个难点：模态关联、实例复杂度、遮挡率差异性。

## 2. 方法论：核心思想与关键技术细节

### 2.1 核心思想
- 提出**SAMBA（SAM-Based Amodal segmentation foundation model）**，是首个基于SAM的零样本amodal分割基础模型。
- 设计**多级促进框架（multilevel facilitation）**，从模态级、实例级、像素级三个层面适配amodal任务特性。

### 2.2 关键技术细节

#### （1）分离-融合结构（Separation-to-Fusion, S2F）- 模态级
- **分离**：在图像编码器中，通过**分离适配器（Separated Adapters）** 并行提取模态特征（modal）和amodal特征。每个适配器使用双对低秩分解矩阵（LoRA），公式：
  - 模态分支：\( h_m = W_0 x_m + W_{mb} W_{ma} x_m \)
  - amodal分支：\( h_a = W_0 x_a + W_{ab} W_{aa} x_a \)
  - 两个独立解码器分别预测模态掩码 \(\tilde{m}_m^i\) 和粗糙amodal掩码 \(\tilde{m}_a^i\)。
- **融合**：后续的**模态融合模块**（一个轻量卷积残差网络）将原始图像、模态预测、amodal预测拼接，输出精细化amodal掩码 \(\tilde{M}_a^i\)。公式：
  \[
  \tilde{M}_a^i = \tilde{m}_a^i + \text{Convs}_K(I, \tilde{m}_m^i, \tilde{m}_a^i)
  \]

#### （2）主目标聚焦机制（Principal Focusing, PF）- 实例级
- 动机：amodal分割需要关注所有深度上的物体，特征提取复杂度高（像素的可能性呈指数增长）。通过指示**主目标（principal object）**，可将任务简化为二元分类。
- 实现：在图像编码器的每个transformer块前插入**主目标聚焦单元**，利用提示嵌入（prompt embeddings）与图像特征进行交叉注意力计算，引导模型聚焦于当前感兴趣的对象。公式：
  - \( Q = W_q x_a \), \( K = W_k E_p \), \( V = W_v E_p \)
  - 计算交叉注意力 \( d_a = \text{softmax}(QK^T/\sqrt{r_a}) V \)
  - 更新特征：\( x_a' = \text{Norm}(x_a + W_{out} d_a) \)
- 提示编码器也设置为可训练以更好适配。

#### （3）遮挡感知的混合专家（Occlusion-Aware MoE）- 像素级
- 动机：不同遮挡率的样本存在冲突特性（低遮挡仅需微小调整，高遮挡需大量补全）。直接混合训练会导致性能妥协。
- 结构：在amodal分支的LoRA中间插入并行卷积专家（Conv-LoRA风格），公式：
  \[
  h_a = W_0 x_a + W_{ab} \left( \sum_{i=1}^N G(W_{aa} x_a)_i E_i(W_{aa} x_a) \right)
  \]
  其中 \(G\) 是门控网络，\(E_i\) 是第 \(i\) 个专家（卷积层）。
- **分布损失（Distribution Loss）**：将遮挡率划分为8个等级（N=8），对每个样本计算其到各等级中心的距离，构造理想门控分数分布 \(S_i = \frac{\log(1/d_i)}{\sum_j \log(1/d_j)}\)。全局地，汇总所有MoE模块中各专家组的实际得分 \(\tilde{S}_i\)，用KL散度最小化分布差异：
  \[
  \mathcal{L}_{\text{dist}} = \text{KL}(\tilde{S}, S)
  \]
  使不同专家专精于不同遮挡率范围。

### 2.3 算法流程说明（文字）
1. 输入：原始图像 \(I\) 和可见部分边界框 \(B_m^i\)。
2. 通过SAM图像编码器（ViT-H）提取特征，其中分离适配器并行输出模态特征和amodal特征（amodal特征中嵌入MoE和PF）。
3. 两个独立解码器分别预测模态掩码和粗糙amodal掩码。
4. 模态融合模块将两者融合，输出最终amodal掩码。
5. 训练损失：分割损失（BCE+Dice）应用于三个预测输出，加上分布损失约束MoE专家分配。

## 3. 实验设计

### 3.1 数据集与场景
- **训练集**：pix2gestalt数据集（837K张图像，基于SA-1B合成遮挡）。
- **测试集**（三个真实遮挡场景）：
  - **COCOA-cls**：80类，3699张图像，分为4个遮挡等级（FG-0~FG-3）。
  - **KINS**：最大amodal街景数据集，14991张图像，2超类7子类。
  - **D2SA**：结账场景，5600张图像，60类。

### 3.2 Benchmark与对比方法
- **零样本方法**：SAM（ICCV‘23）、SDXL-Inpainting（ICLR‘24）、pix2gestalt（CVPR‘24）。
- **全监督方法**：C2F-Seg（ICCV‘23）、SDAmodal（CVPR‘24）。
- **公平对比**：所有方法均使用预测的模态掩码（而非GT）作为输入，更贴近实际应用。

### 3.3 评价指标
- **性能**：平均IoU（mean IoU）。
- **效率**：参数量（Params）、推理时间（Time）。

## 4. 资源与算力
- **训练配置**：8块NVIDIA A100 Tensor Core GPU，训练10个epoch。
- **优化器**：AdamW（β1=0.9, β2=0.999, weight decay=0.1）。
- **学习率**：初始1e-4（经过250步热身），余弦衰减至0。
- **模型**：基于ViT-H版本SAM，可训练参数72M（相比pix2gestalt的860M大幅降低）。

## 5. 实验数量与充分性

### 5.1 实验组数
- **主对比实验**：在3个数据集上对比5种方法（含3种零样本、2种全监督），报告mean IoU、参数量、速度（表2）。
- **消融实验**：
  - S2F和PF的消融（表3）：4组设置。
  - MoE和分布损失的消融（表4）：3组设置。
  - 不同适配器秩的尝试（表6）：3组设置。
  - 输入框质量影响测试：随机扰动±5%、±10%，报告稳定性。
  - 专门模型（按遮挡率训练）与全数据训练对比（表5）：4组设置。
- **定性结果**：图5展示多场景可视化对比。

### 5.2 充分性与公平性
- **充分性**：覆盖了关键组件（S2F、PF、MoE、Dist Loss）的消融，验证了每个设计的贡献。对超参数（秩、专家数、遮挡等级划分）进行了探索。测试了输入框噪声鲁棒性。
- **客观公平**：对比方法均采用预测的模态掩码输入（消除不公平优势）；所有实验在相同测试集上零样本评估（模型未见真实场景）。训练集（合成）与测试集（真实）分布不同，符合零样本设定。

## 6. 主要结论与发现
- **性能领先**：SAMBA在COCOA-cls、KINS、D2SA上分别达到81.82%、88.47%、90.87% mean IoU，**超越所有零样本方法和全监督方法**，成为新SOTA。
- **高效性**：仅72M可训练参数，推理时间0.3秒/实例（接近SAM，比pix2gestalt快300倍以上）。
- **组件有效性**：
  - S2F结构提升2.46%（对比纯LoRA微调）。
  - PF机制在高遮挡率（FG-3）提升约3%，整体提升0.74%。
  - MoE+分布损失在标准MoE基础上再提0.54%，尤其在高遮挡率下效果显著。
- **鲁棒性**：对输入边界框扰动（±10%）性能仅下降0.70%，表现稳定。

## 7. 优点

### 7.1 方法亮点
1. **首个SAM基础amodal模型**：有效利用SAM的通用分割能力，无需复杂扩散模型。
2. **多级设计针对性强**：模态级（S2F）、实例级（PF）、像素级（MoE）分别解决amodal特有挑战，逻辑清晰且耦合度低。
3. **遮挡感知MoE + 分布损失**：创新地将遮挡率作为专家分配先验，通过KL散度引导专家专业化，避免了传统MoE的负载失衡问题。
4. **参数高效**：仅微调LoRA适配器和少量新增模块（72M），冻结SAM主干，实现高效训练和推理。

### 7.2 实验亮点
- **全面且公平**：对比5种代表性方法，统一输入条件，覆盖3个不同场景（街景、结账、通用）。
- **消融充分**：每个组件独立验证，并检验超参数影响（秩、专家数量等）。
- **鲁棒性分析**：测试输入框噪声，证明模型在实际应用中的稳定性。
- **可视化清晰**：定性结果展示了复杂遮挡场景下的优越补全能力。

## 8. 不足与局限

### 8.1 实验覆盖方面
- **训练数据局限**：pix2gestalt是合成数据，可能与真实遮挡分布存在偏差，论文未讨论该偏差导致的潜在风险（例如对某些罕见遮挡模式泛化性不足）。
- **遮挡等级划分**：默认8级（0,0.01,0.1,0.2,0.3,0.4,0.5,0.75,1.0），但未探索其他划分策略的影响（如非等距或自适应划分）。
- **未测试极端情况**：完全遮挡（遮挡率=1）的样本在数据中极少，模型能力未单独评估。

### 8.2 偏差风险
- **类别偏差**：COCOA-cls、KINS、D2SA均基于COCO/KITTI/D2S，类别有限，开放世界中长尾类别表现未验证。
- **实例级偏差**：模型依赖可见部分边界框作为提示，若边界框不准确（如偏离较大）或目标极小，性能可能下降更显著（论文仅测试±10%扰动）。
- **专家专业化验证不足**：虽证明MoE整体有效，但未可视化每个专家是否真的对应特定遮挡率区间。

### 8.3 应用限制
- **仅二值掩码**：输出为amodal掩码，不提供类别标签，语义理解需结合其他模型。
- **多实例场景**：输入为单实例边界框，对于密集遮挡场景需逐个处理，效率可能降低（但论文未讨论）。
- **部署限制**：基于ViT-H，虽参数少但需GPU推理（文中使用A100），边缘设备部署可能仍困难。

### 8.4 其他
- **代码和模型未开源**：论文未提及是否计划开源（截止到2025年6月），影响可复现性。
- **对比的全监督方法较老**：C2F-Seg（2023）、SDAmodal（2024），但仍有竞争力，未提及更近期的全监督工作。

---

（完）
