---
title: "Segment Anyword: Mask Prompt Inversion for Open-Set Grounded Segmentation"
title_zh: "Segment Anyword: 掩码提示反转用于开放集语义分割"
authors: "Zhihua Liu, Amrutha Saseendran, Lei Tong, Xilin He, Fariba Yousefi, Nikolay Burlutskiy, Dino Oglic, Tom Diethe, Philip Alexander Teare, Huiyu Zhou, Chen Jin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9bzgpYtQZn"
tags: ["query:mmseg"]
score: 9.0
evidence: 利用扩散模型掩码提示反转进行开放集语义分割
tldr: 该论文提出Segment Anyword，一种无需训练的开放集语言引导分割方法。利用冻结扩散模型的token级交叉注意力图生成掩码提示，并细化得到目标掩码。该方法无需微调即可分割任意文本描述的物体，在多个开放集分割基准上达到最先进性能，为语义分割提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1674, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 850, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 876, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 815, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 894, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1048, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1504, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1762, \"height\": 1643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1737, \"height\": 1308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1767, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1057, \"height\": 1287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1074, \"height\": 1218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1417, \"height\": 1401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1071, \"height\": 1524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1295, \"height\": 1501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1269, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1724, \"height\": 1987, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1240, \"height\": 2202, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1224, \"height\": 2220, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1671, \"height\": 2126, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1041, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1247, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9bzgpytqzn/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1132, \"height\": 1680, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 874, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 681, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 540, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 802, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 463, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 748, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 583, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9bzgpytqzn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1297, \"height\": 282, \"label\": \"Table\"}]"
motivation: 现有开放集分割方法需要大量训练或微调，且难以统一分割多样文本表述的物体。
method: 利用冻结扩散模型的交叉注意力图生成掩码提示，并通过提示细化得到精确掩码。
result: 在多个开放集分割数据集上，Segment Anyword无需微调即达到最优性能。
conclusion: 该工作为开放集语言引导分割提供了高效的无训练方案。
---

## Abstract
Open-set image segmentation poses a significant challenge because existing methods often demand extensive training or fine-tuning and generally struggle to segment unified objects consistently across diverse text reference expressions. Motivated by this, we propose Segment Anyword, a novel training-free visual concept prompt learning approach for open-set language grounded segmentation that relies on token-level cross-attention maps from a frozen diffusion model to produce segmentation surrogates or *mask prompts*, which are then refined into targeted object masks. Initial prompts typically lack coherence and consistency as the complexity of the image-text increases, resulting in suboptimal mask fragments. To tackle this issue, we further introduce a novel linguistic-guided visual prompt regularization that binds and clusters visual prompts based on sentence dependency and syntactic structural information, enabling the extraction of robust, noise-tolerant mask prompts, and significant improvements in segmentation accuracy. The proposed approach is effective, generalizes across different open-set segmentation tasks, and achieves state-of-the-art results of 52.5 (+6.8 relative) mIoU on Pascal Context 59, 67.73 (+25.73 relative) cIoU on gRefCOCO, and 67.4 (+1.1 relative to fine-tuned methods) mIoU on GranDf, which is the most complex open-set grounded segmentation task in the field.

---

## 论文详细总结（自动生成）

# 论文总结：《Segment Anyword: Mask Prompt Inversion for Open-Set Grounded Segmentation》

## 1. 核心问题与整体含义（研究动机和背景）

开放集图像分割（Open-set image segmentation）要求模型能根据任意自然语言描述分割出图像中的目标物体，而不仅仅是预定义的固定类别。现有方法主要分为三类：

- **CLIP-based**：需要训练或微调额外的编码器/解码器，计算资源高。
- **MLLM-based**（如 LISA、GLaMM、OMG-LLaVA）：虽然性能优秀，但通常需要大规模训练（参数数亿至数十亿），且对于训练时未见过的词汇或短语（如领域特定术语）表现不稳定。
- **Prompt-based**（如 SAM4MLLM）：仍需微调，且难以处理复杂文本描述。

这些方法普遍存在两个问题：**（1）需要大量训练或微调，资源消耗大；（2）当文本描述变化时（如同义词替换、不同领域术语），分割结果不稳定、不一致。** 作者通过一个动机研究（Motivational Study）证实了这一点：对同一图像-文本对的不同变体（如“apple pieces” → “apple slices”），VLM/MLLM 的 IoU 均值低且标准差高，表明分割性能对文本表述的敏感性高。

为此，本文提出 **Segment Anyword**，一种**无需训练（training-free）** 的开放集语言引导分割方法，核心思想是利用**冻结的扩散模型**中的 token 级交叉注意力图来生成“掩码提示”（mask prompts），再通过下游可提示分割器（如 SAM）细化得到精确掩码。该方法仅需在测试时优化极少量文本嵌入参数，能够适应任意新词汇和视觉概念，显著降低了资源需求并提高了对文本变体的鲁棒性。

## 2. 方法论

### 核心思想

利用一个**冻结的文本到图像扩散模型**（如 Stable Diffusion）作为先验知识库。给定输入图像和文本描述，先通过**文本反转（Textual Inversion）** 优化目标名词对应的文本嵌入向量，使嵌入更好地对齐图像中的视觉概念；然后在去噪过程中收集所有时间步的**平均交叉注意力图**，将其作为粗略的物体定位先验（即掩码提示）；最后从高响应区域随机采样点输入到**冻结的 SAM** 中，生成精确的物体掩码。

### 关键技术细节

1. **文本嵌入优化**：
   - 输入文本解析为名词短语（NP）、形容词、其他助词。只优化与目标视觉概念对应的名词和形容词的嵌入向量 \( \mathbf{V} = [\mathbf{v}^*,\dots,\mathbf{v}^\&] \)。
   - 优化目标为扩散模型的去噪损失（仅更新嵌入，冻结文本编码器 \( c_\phi \) 和去噪网络 \( \epsilon_\theta \)）：
     \[
     \mathcal{L}_{\text{DM}} = \mathbb{E}_{z,\epsilon,\mathbf{V},t} \left[ \|\epsilon - \epsilon_\theta(z_t, t, \mathbf{V})\|^2 \right]
     \]
   - 使用直接反转（Direct Inversion）从输入图像生成确定性噪声潜变量 \( z^\star \)，作为测试时输入。

2. **交叉注意力图收集**：
   - 在去噪过程中，对于每个目标名词 token，计算其与图像嵌入的交叉注意力图 \( \mathbf{M}_t \)。
   - 对所有时间步求平均，得到平均注意力图 \( \bar{\mathbf{M}} \)。
   - 对 \( \bar{\mathbf{M}} \) 进行硬阈值（0.7），从最大连通区域中随机采样点作为 SAM 的正点提示。

3. **语言引导的视觉提示正则化**：
   - **Positive Adjective Prompt Clustering**：将形容词的交叉注意力图与对应名词的注意力图聚类，作为正点对，增强掩码完整性（例如“blue sweatshirt”的“blue”与“sweatshirt”关联）。
   - **Negative Mutual Exclusive Prompt Binding**：利用句子句法结构，将互斥实体（如不同宾语）的提示作为负点输入，帮助区分不同物体的边界。对于单一物体，从背景区域随机采样 1-3 个负点。
   - 这些正则化直接利用了句子的**依存关系**和**句法结构**，无需额外训练。

4. **后处理**：
   - 使用冻结的 **SAM (ViT-H)** 作为可提示掩码生成器，将点提示输入后输出最终分割掩码。

### 算法流程（文字描述）

1. 输入图像 \( x \)、文本表达式 \( s \)。
2. 使用 LLM（如 Vicuna-7B）或 NLP 库解析句子，提取名词短语、形容词和根名词。
3. 初始化文本嵌入（使用 BERT 预训练嵌入）。
4. 冻结扩散模型，仅优化目标名词和形容词的嵌入，最小化去噪损失（步骤 2-3 可循环 S 次）。
5. 执行图像反转得到噪声潜变量序列。
6. 对反转后的潜变量进行去噪，收集所有时间步的交叉注意力图，平均得到 \( \bar{\mathbf{M}} \)。
7. 对每个目标概念，从 \( \bar{\mathbf{M}} \) 的高响应区域采样点（正点），并从互斥概念区域采样负点。
8. 将正/负点输入 SAM，生成掩码。

## 3. 实验设计

### 数据集与场景

| 任务 | 数据集 | 评估指标 |
|------|--------|----------|
| 开放集语言引导分割 | **GranDf**（验证/测试集，214K 图像-文本对） | AP50, mIoU, Recall |
| 多目标参考分割 | **gRefCOCO**（278K 表达式） | cIoU, gIoU |
| 单目标参考分割 | **RefCOCO, RefCOCO+, RefCOCOg**（各约 14 万表达式） | cIoU |
| 开放词汇语义分割 | **Pascal Context 59**（PC-59，59 类） | mIoU |

### 对比方法

- **端到端 MLLM**：BuboGPT、Kosmos-2、LISA、GLaMM、OMG-LLaVA。
- **微调 MLLM**：GLaMM\(_f\)、OMG-LLaVA\(_f\)。
- **训练-免方法**：CLIPasRNN、PSALM (Zero-Shot)、OVDiff、EmerDiff、CaR 等。
- **传统方法**：MattNet、LAVT、CRIS、ETRIS、ReLA、GSVA、SAM4MLLM 等。

### 结果亮点

- **GranDf Val**：AP50 31.3, mIoU 67.4（优于所有微调方法 GLaMM: 66.3 mIoU）。
- **gRefCOCO**：cIoU 67.73（+25.73 relative），超过 SAM4MLLM (66.33)。
- **Pascal Context 59**：mIoU 52.5（+6.8 relative），优于所有训练-免扩散方法（EmerDiff: 45.7）。
- **RefCOCO/+/g**：虽然训练-免方法不如微调方法，但远优于其他零样本方法（如 GL-CLIP, CLIPasRNN）。

## 4. 资源与算力

文中提及：
- **硬件**：单个 40G A100 GPU。
- **超参数**：批量大小 8，基础学习率 0.005，温度与缩放参数 (0.3, 0.00075)。
- **文本嵌入更新**：默认 1100 步；使用 LoRA 微调 BERT 文本编码器（500 图像-文本对）后，推理时可减少到 50 步，大幅加速（470s → 28s）。
- **LoRA 配置**：rank=16，仅微调 BERT 编码器。
- **LLM 用于解析**：Vicuna-7B-v1.5（冻结）。

**训练时长未明确给出**，但声称“无需大规模训练或微调”，主要开销在测试时文本嵌入优化（1100 步，约 470s）或 LoRA 加速版（50 步，约 28s）。相比于需要训练数小时的 MLLM 方法（如 GLaMM 需 11M 图像），本方法资源需求极低。

## 5. 实验数量与充分性

论文进行了非常丰富的实验：
- **主要结果**：覆盖 6 个数据集，4 种任务类型，与 15+ 种方法对比。
- **消融实验**（Table 6）：分别验证 SAM 后处理、文本嵌入更新、正形容词聚类、负互斥绑定的贡献。
- **附加分析**：
  - 不同扩散骨干网络（SD 1.4/1.5）和反转算法（DDIM, Null-text Inversion）的兼容性。
  - 不同 POS 解析工具（GPT-4o, SpaCy, Vicuna）的影响。
  - 使用 GLaMM 生成文本 vs. 真实文本的对比。
  - 纯文本提示 vs. 本方法提示（LangSAM 对比）。
  - 开放集新颖概念和噪声文本的压力测试。
  - 谓词分割（“pulling”“holding”）的可视化。
  - 失败案例分析（小物体、低分辨率16×16）。
- **统计充分性**：每个实验在各自的官方验证/测试集上进行，结果可信。对比方法均使用原论文汇报的最好结果，且与训练-免方法公平对比。

**实验设计客观、公平**，消融实验清晰，充分证明了各模块的有效性。

## 6. 主要结论与发现

- Segment Anyword 作为**第一个完全训练-免**的开放集语言引导分割框架，在 GranDf、gRefCOCO、Pascal Context 上均达到或超越当前最好（包括许多需要大规模微调的方法）。
- **关键发现**：利用冻结扩散模型的交叉注意力图即可获得有效的物体定位先验；通过语言引导的提示正则化能显著提升掩码质量，消除碎片化。
- **泛化能力**：不仅能分割名词实体，还能分割谓词（如动作关系），适用于开放集、参考图像、乃至 OOD 医学图像分割。
- **效率**：仅更新少量文本嵌入参数（<0.1M 可训练参数），计算开销低。

## 7. 优点

1. **训练-免**：无需任何训练数据的标签或微调，降低了部署成本。
2. **轻量**：测试时仅优化少量嵌入，相比于微调大型 MLLM（数十亿参数）节省资源。
3. **可解释性**：交叉注意力图直接显示文本与图像区域的关联。
4. **语言引导的正则化**创新性地将句法依存结构引入视觉提示，简单有效，提升了掩码完整性和边界区分度。
5. **模块化设计**：扩散模型和 SAM 均可替换，易于扩展（如更换高分辨率骨干）。
6. **强泛化**：对未见过的词汇、领域特定术语、噪声文本都有良好鲁棒性。
7. **谓词分割**：首次实现无需额外训练的动作/关系分割。

## 8. 不足与局限

1. **小物体分割困难**：由于交叉注意力图分辨率低（16×16），微小或细长物体（如“skis”“skateboard”）定位不准确，导致 SAM 难以生成精细掩码。
2. **推理速度较慢**：默认 1100 步优化约 470s，虽然 LoRA 加速版降至 28s，但仍高于某些实时方法。未来可借助更高效的扩散模型（如 Hyper-SD）进一步提速。
3. **依赖语言解析工具**：使用 LLM 或 NLP 库进行短语解析，解析错误会影响结果（如形容词遗漏）。尽管作者指出可用 GPT-4o 高准确度解析，但增加了外部依赖和潜在成本。
4. **开放性词汇限制**：对于完全未见过的词汇（如随机字符串），文本嵌入初始化可能不理想，尽管测试时优化可以部分补偿，但效果可能下降。
5. **缺乏对关系推理的定量评估**：谓词分割仅有定性示例，没有定量指标。
6. **对比不完全**：在 RefCOCO/+/g 上，训练-免方法整体低于微调方法（这是合理的），但论文未深入分析为什么在单目标参考分割上差距较大（可能是单一掩码任务基准较高的原因）。
7. **冗余计算**：虽然在测试时优化，但扩散模型的前向传播需要多次，计算量仍高于简单前馈网络。

（完）
