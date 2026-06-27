---
title: "JarvisIR: Elevating Autonomous Driving Perception with Intelligent Image Restoration"
title_zh: JarvisIR：利用智能图像恢复提升自动驾驶感知
authors: "Lin, Yunlong, Lin, Zixu, Chen, Haoyu, Pan, Panwang, Li, Chenxin, Chen, Sixiang, Wen, Kairun, Jin, Yeying, Li, Wenbo, Ding, Xinghao"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Lin_JarvisIR_Elevating_Autonomous_Driving_Perception_with_Intelligent_Image_Restoration_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 4.0
evidence: VLM驱动的自动驾驶感知恢复智能体
tldr: 自动驾驶视觉感知在恶劣天气下退化严重。本文提出JarvisIR，以VLM(如Llava-Llama3)作为控制器，协同多个专家恢复模型，并通过微调和人类反馈对齐提升鲁棒性，实现无退化先验的通用图像恢复。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1692, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 881, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 827, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1796, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 841, \"height\": 867, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1783, \"height\": 973, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-lin-jarvisir-elevating-autonomous-driving-perception-with-intelligent-image-restoration-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 838, \"height\": 335, \"label\": \"Table\"}]"
motivation: 现有恢复方法依赖特定先验或存在域差距，难以应对复杂天气退化。
method: 以VLM为控制器管理多个恢复专家，结合微调与人类反馈对齐。
result: 在多种恶劣天气恢复和下游感知任务上取得最佳效果。
conclusion: VLM作为控制器可有效集成多种恢复专家，提升自动驾驶鲁棒性。
---

## Abstract
Vision-centric perception systems often struggle with unpredictable and coupled weather degradations in the wild. Current solutions are often limited, as they either depend on specific degradation priors or suffer from significant domain gaps. To enable robust and autonomous operation in real-world conditions, we propose JarvisIR, a VLM-powered agent that leverages the VLM (e.g., Llava-Llama3) as a controller to manage multiple expert restoration models. To further enhance system robustness, reduce hallucinations, and improve generalizability in real-world adverse weather, JarvisIR employs a novel two-stage framework consisting of supervised fine-tuning and human feedback alignment. Specifically, to address the lack of paired data in real-world scenarios, the human feedback alignment enables the VLM to be fine-tuned effectively on large-scale real-world data in an unsupervised manner. To support the training and evaluation of JarvisIR, we introduce CleanBench, a comprehensive dataset consisting of high-quality and large-scale instruction-responses pairs, including 150K synthetic entries and 80K real entries. Extensive experiments demonstrate that JarvisIR exhibits superior decision-making and restoration capabilities. Compared with existing methods, it achieves a 50% improvement in the average of all perception metrics on CleanBench-Real.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究动机**：自动驾驶中的视觉感知系统在真实世界的恶劣天气（如雨、雪、雾、夜间）下，会遭遇多种耦合的退化（例如同时存在雨滴、模糊、噪声）。现有方法包括针对单一退化的任务专用方法和统一处理多种退化的全合一方法，但两者均存在明显局限：任务专用方法需预先知道退化类型，无法应对未知的耦合退化；全合一方法通常在合成数据上监督训练，迁移到真实数据时面临严重的域差距，导致性能下降。
*   **整体含义**：本文旨在构建一个能够自主、鲁棒、无退化先验地恢复真实世界复杂退化图像的智能系统。核心思路是利用视觉语言模型（VLM）作为控制器，动态协调多个公开的专家恢复模型，并设计有效的微调与对齐策略来提升系统在真实环境中的泛化能力。

### 2. 论文提出的方法论

*   **核心思想**：将VLM（具体为Llava-Llama3-8B）作为智能体，通过“任务规划→模型选择→任务执行→响应生成”四步流水线，为每张输入图像自主决策最优的任务顺序和模型组合，从而调用多个专家模型（如去噪、去雨、去雾、低光增强、去雪等）依次处理，最终输出高质量恢复图像。
*   **关键技术细节**：
    1.  **CleanBench数据集**：构建了大规模指令-响应配对数据集，包含150K合成样本（用于监督微调）和80K真实样本（用于对齐训练）。每对数据包括用户指令、退化图像和标准响应（含链式思维推理与最优任务序列）。真实样本覆盖雨、夜、雪、雾四种复杂场景，且无配对标签。
    2.  **两阶段训练框架**：
        *   **第一阶段：监督微调（SFT）** 在合成CleanBench上训练JarvisIR-SFT，使其学会根据用户指令识别退化、规划任务并选择模型。
        *   **第二阶段：人类反馈对齐（MRRHF算法）** 在真实CleanBench-Real上无监督微调，提升鲁棒性、减少幻觉、增强泛化。MRRHF是对RRHF方法的扩展，核心有三：
            *   **混合样本生成策略**：同时使用离线（从SFT模型用多样波束搜索预生成）和在线（训练中从当前策略模型采样）的候选响应，兼顾探索空间与性能下限。
            *   **奖励模型**：集成多个VLM-based IQA模型（Q-instruct、MUSIQ、MANIQA），通过z-score标准化后对恢复结果打分。
            *   **损失函数**：结合排序损失（L_rank）、最优响应的交叉熵损失（L_ft）以及熵正则化项（L_er），鼓励响应多样性，防止训练坍塌。
    3.  **算法流程**：对每个输入，生成候选响应集，执行任务序列得到恢复图像，由奖励模型评分。然后通过排序损失让模型给予高分响应更高概率，低分响应更低概率，同时用交叉熵学习最佳响应，并用熵正则化维持多样性。

### 3. 实验设计

*   **数据集与场景**：使用自建的CleanBench-Real验证集（2K图像，来自4种天气场景：夜、雨、雾、雪），每种场景均包含多种耦合退化。无配对ground truth，因此使用无参考图像质量评估（IQA）指标评估恢复质量。
*   **对比方法**：
    *   **决策能力对比**：5种策略（随机顺序与模型、随机顺序+预测模型、随机模型+预测顺序、人类专家预设顺序、人类专家逐例定制），评估Score与Ranking。
    *   **感知恢复对比**：7种全合一恢复方法（AirNet、AutoDIR、DA-CLIP、PromptIR、MiOIR、InstructIR、T3-DiffWeather）。
    *   同时与自身的SFT版本和MRRHF版本进行对比。
*   **评价指标**：MUSIQ、MANIQA、CLIP-IQA+、LIQE四项无参考IQA指标。决策能力用Score（指标总和）和Ranking（在全部可能决策中的百分比排名）评估。

### 4. 资源与算力

*   文中明确说明实验在 **8 块 NVIDIA A100 80G GPU** 上进行。
*   **SFT阶段**：训练3个epoch，batch size 128，学习率1e-5。
*   **MRRHF阶段**：训练3个epoch，batch size 1，学习率1e-5，多样波束搜索大小3，组数5，多样性惩罚2.0，采样温度0.8。
*   未提供总训练时间，但可推测由于全参数微调且数据量大，算力需求较高。

### 5. 实验数量与充分性

*   **主要对比实验**：
    *   决策能力对比：Table 1，比较5种人工策略及JarvisIR两个版本，证明MRRHF版本最优（Ranking 4.8%）。
    *   感知恢复对比：Table 2，在4种天气场景下与7种全合一方法对比，JarvisIR-MRRHF在所有指标上全面领先，平均提升约50%。
    *   消融实验：Table 3与Figure 7，围绕MRRHF中的样本生成策略（离线/在线/混合）和熵正则化，分析对奖励分数和多样性的影响。
    *   视觉比较：Figure 6展示真实图像恢复效果，定性验证。
*   **充分性评价**：实验覆盖了决策质量、恢复质量、消融分析，对比了多种代表性基线，且消融实验验证了核心改进的有效性。但未与其他同期的智能体恢复方法（如RestoreAgent、AgenticIR）进行直接比较，这些工作也是CVPR/arXiv同期，作者在Related Work中提到但未在实验部分对比，略显不足。整体上实验设计合理、客观，结论有说服力。

### 6. 论文的主要结论与发现

1.  **JarvisIR-MRRHF在决策能力和感知恢复能力上均显著优于所有对比方法**，在CleanBench-Real上所有感知指标平均提升50%（对比现有全合一方法）。
2.  **人类反馈对齐（MRRHF）有效减少了VLM的幻觉，提升了系统在真实环境下的泛化能力**，MRRHF版本在Score和Ranking上均优于SFT版本。
3.  **混合样本生成策略比纯离线或纯在线策略更优**，能扩大探索空间同时保持训练稳定；**熵正则化有助于增加响应多样性**，进一步提升对齐效果。
4.  **JarvisIR能够自主、动态调度专家模型**，超越依赖先验或固定顺序的静态方案，甚至优于人类专家提供的定制方案。

### 7. 优点

*   **方法创新性**：首次将VLM作为智能体集成多专家恢复模型，并设计两阶段无监督对齐训练框架，解决真实数据无配对标签的难题。
*   **数据集贡献**：构建了首个大规模、高质量、覆盖合成与真实的指令-响应数据集CleanBench（230K样本），可推动后续研究。
*   **算法设计精细**：MRRHF中的混合采样、熵正则化、多IQA奖励模型等设计，有效平衡了探索与利用，避免了训练不稳定。
*   **实验全面性**：涵盖了决策能力与感知恢复两方面的定量与定性评估，消融实验验证了关键组件。
*   **实用价值高**：方法直接面向真实自动驾驶场景，展现出良好的鲁棒性与泛化能力。

### 8. 不足与局限

*   **对比基准覆盖不全**：未与同期智能体恢复系统（如RestoreAgent, AgenticIR）进行实验对比，削弱了方法先进性论证的完整性。
*   **专家模型选择受限**：实验仅使用了轻量级模型（如IDT, SCUnet等），若采用更先进的SOTA专家模型，性能可能进一步提升，但本文主要验证框架有效性，模型可替换。
*   **真实场景评价依赖无参考指标**：由于无配对准真实值，仅使用IQA指标，可能存在与人类主观感受不完全一致的风险。虽使用了多种IQA综合评分，但缺乏用户研究验证。
*   **计算资源需求高**：全参数微调8B模型需8块A100，计算开销较大，可能限制其在实际部署中的适用性。
*   **幻觉问题未完全消除**：尽管MRRHF减少了幻觉，但在极端复杂场景下VLM仍可能输出错误的任务序列或模型调用，系统鲁棒性仍有提升空间。

（完）
