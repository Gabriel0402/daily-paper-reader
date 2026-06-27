---
title: "M³HF: Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality"
title_zh: "M³HF: 来自混合质量多阶段人类反馈的多智能体强化学习"
authors: "Ziyan Wang, Zhicheng Zhang, Fei Fang, Yali Du"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2Sl6Ex7Vmo"
tags: ["query:vlm-rl"]
score: 8.0
evidence: 利用LLM解析人类反馈的多智能体强化学习
tldr: 多智能体强化学习面临奖励设计困难。该文提出M3HF框架，引入多阶段混合质量人类反馈，利用大语言模型解析反馈信息，迭代优化智能体策略。在协调任务中，该方法有效纠正了非最优行为，提升任务性能，为结合自然人交互的MARL提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1699, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1727, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1057, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 667, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1697, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2sl6ex7vmo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1620, \"height\": 904, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 888, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 885, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2sl6ex7vmo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 884, \"height\": 492, \"label\": \"Table\"}]"
motivation: 现有MARL奖励函数设计复杂且易导致次优行为。
method: 用LLM解析人类评价文本，在多阶段训练中暂停学习以接收反馈。
result: 在复杂协作环境中策略对齐和性能优于基线。
conclusion: 混合质量人类反馈能有效引导MARL，LLM作为接口。
---

## Abstract
Designing effective reward functions in multi-agent reinforcement learning (MARL) is a significant challenge, often leading to suboptimal or misaligned behaviors in complex, coordinated environments. We introduce Multi-agent Reinforcement Learning from Multi-phase Human Feedback of Mixed Quality ($\text{M}^3\text{HF}$), a novel framework that integrates multi-phase human feedback of mixed quality into the MARL training process. By involving humans with diverse expertise levels to provide iterative guidance, $\text{M}^3\text{HF}$ leverages both expert and non-expert feedback to continuously refine agents' policies. During training, we strategically pause agent learning for human evaluation, parse feedback using large language models to assign it appropriately and update reward functions through predefined templates and adaptive weights by using weight decay and performance-based adjustments. Our approach enables the integration of nuanced human insights across various levels of quality, enhancing the interpretability and robustness of multi-agent cooperation. Empirical results in challenging environments demonstrate that $\text{M}^3\text{HF}$ significantly outperforms state-of-the-art methods, effectively addressing the complexities of reward design in MARL and enabling broader human participation in the training process.

---

## 论文详细总结（自动生成）

# 论文总结：M³HF: 多智能体强化学习中的混合质量多阶段人类反馈

## 1. 核心问题与整体含义（研究动机与背景）

- 多智能体强化学习（MARL）中，奖励函数设计是一个关键挑战：稀疏或复杂的奖励信号会导致智能体收敛缓慢或陷入次优策略。
- 现有方法依赖手工奖励设计或单一阶段的人类偏好，难以处理多智能体协调场景中的非平稳性和任务复杂度。
- 论文提出 **M³HF** 框架，通过引入**多阶段、混合质量的人类反馈**（既包含专家也包含非专家反馈），利用大语言模型（LLM）解析反馈并动态调整奖励函数，从而提升多智能体协作性能。
- 核心含义：将人类自然语言反馈在线、迭代地融入MARL训练流程，使非专家也能参与指导，降低奖励设计难度，提高策略对齐的鲁棒性。

## 2. 方法论

- **核心思想**：基于马尔可夫博弈扩展为多阶段人类反馈马尔可夫博弈（MHF-MG），增加人类反馈集 \(U\) 和人类策略 \(\pi_h\)。在每一代（generation）训练后，智能体暂停学习并生成 rollout 视频供人类评估；人类提供自然语言反馈；LLM 解析反馈并分配给特定智能体或全体智能体；然后基于预定义奖励模板生成新的奖励函数，并通过权重衰减和性能调整机制动态组合到奖励池中。
- **关键技术细节**：
  - **Rollout 生成**：每隔固定训练迭代，生成 \(X\) 条独立轨迹 \(\tau_k\)，作为人类评估依据。
  - **反馈解析**：使用 LLM（如 GPT-4o）将人类自然语言 \(u_k\) 解析为针对各智能体的指令 \(u_i^k\) 和全局指令 \(u_{\text{all}}^k\)。
  - **奖励模板**：预定义距离、动作、状态、时间、成功等模板（如 \(f_{\text{dist}} = -\|s[e1.pos] - s[e2.pos]\|_2\)），LLM 根据反馈选择并参数化。
  - **奖励池与权重更新**：
    - 每个智能体维护奖励函数池 \(P_i\)，新奖励函数加入后初始化权重 \(w_{i,m} = 1/|P_i|\)。
    - 对原有权重施加指数衰减 \(w_{i,m} = w_{i,m} \cdot \alpha^{M-m}\)。
    - 根据相邻代在原始奖励上的性能差 \(\Delta r_i = r_{\text{ori}}^{k+1} - r_{\text{ori}}^k\) 调整新奖励权重：若性能提升则增加 \(\beta\)，否则减少（不低于0）。
    - 最终奖励函数 \(\hat{R}_i^{k+1} = \sum_m w_{i,m} R_{i,m}\)。
  - **理论分析**：证明使用 rollout 估计性能的收敛性，以及权重机制对低质量反馈的鲁棒性（Proposition 4.2）：低质量反馈最多造成一次有界退化，而高质量反馈贡献可累积。
- **算法流程**（Algorithm 1）：
  1. 初始化奖励池为原始奖励。
  2. 对每代 \(k\)：
     - 使用当前奖励函数训练策略（IPPO）若干迭代。
     - 生成 rollout 视频。
     - 人类提供反馈 \(u_k\)。
     - LLM 解析 → 生成新奖励函数 → 加入池 → 更新权重 → 形成下一代奖励。

## 3. 实验设计

- **环境与任务**：Overcooked 变体（7×7网格，3个智能体协作制作沙拉并送达）：
  - 三种厨房布局（A、B、C），难度递增。
  - 两种食谱：Lettuce-Tomato 沙拉、Lettuce-Onion-Tomato 沙拉。
  - 智能体使用宏动作（基于 Xiao et al. 2022），部分观测（5×5视野）。
  - 奖励：仅正确沙拉 +200，错误 -50，每步 -0.1。
- **基准方法**：
  - MAPPO（Yu et al. 2022）
  - IPPO（De Witt et al. 2020）
  - Macro-Action-Based Baseline（Mac-IAICC 和 Mac-CAC 的平均性能）
  - 消融实验还对比了：IRAT（内在奖励方法，三种变体 rw1/rw2/rw3）、单阶段反馈、无权重调整等。
- **评估指标**：平均 episode return（原始奖励下）随训练迭代的变化。
- **额外实验**：在 Google Research Football (GRF) 5v5 HARD 场景中验证可扩展性，比较胜率、拦截、射门等指标。

## 4. 资源与算力

- 论文明确提到：实验在**异构计算集群**上运行，操作系统 Ubuntu Linux。
- CPU：Dual Intel Xeon E5-2650 / E5-2680 v2 / E5-2690 v3 等多款型号，共 180 个核心。
- GPU：**3 块 NVIDIA A30 GPU**。
- 系统内存：500 GB。
- **训练时间**：未明确给出单次实验的具体训练时长，但每代包含 200 迭代，每迭代 25 个 episode，每 episode 最多 200 步，总训练约 25k episodes（1000 迭代）。论文未报告总训练天数。

## 5. 实验数量与充分性

- **主要实验组**：
  - 6 组主实验（3 种布局 × 2 种食谱），每种 3 个随机种子 → 共 18 条学习曲线。
  - 混合质量反馈实验（低质量、VLM 反馈）在 Overcooked-B + Lettuce-Onion-Tomato 上进行。
  - 消融实验：
    1. 反馈解析 vs. 原始反馈 vs. 全流程（LLM + 权重调整）。
    2. 单阶段 vs. 多阶段反馈。
    3. 与内在奖励方法 IRAT 对比。
  - 扩展实验：GRF 5v5 场景。
- **充分性评价**：
  - **充分**：覆盖了不同布局复杂度、不同食谱、多种基准方法，并设计了消融验证各组件贡献。
  - **客观公平**：所有基准方法均进行了超参数调优（学习率、批大小等），宏动作基线直接采用原论文最佳超参数，随机种子重复 3 次报告均值和标准差。
  - 但未在更多元的环境（如多智能体导航、战斗任务）中验证泛化性。

## 6. 主要结论与发现

1. **性能领先**：M³HF 在所有 Overcooked 场景中均显著优于 MAPPO、IPPO 和宏动作基线，尤其在复杂布局和配方下优势更大。
2. **多阶段优于单阶段**：多次迭代反馈比仅一次初始反馈带来更大幅度的性能提升。
3. **结构化解析与权重调整关键**：直接使用原始反馈（无LLM解析）效果差；加入权重调整后性能进一步提升。
4. **对低质量反馈鲁棒**：即使提供无效的错误反馈，M³HF 性能仅略低于 IPPO 基线，不会严重退化（支持理论分析）。
5. **VLM 替代人类有限**：当前 VLM（Gemini 1.5 Pro）提供的反馈不够具体，难以有效指导奖励塑造，效果接近无反馈。
6. **内在奖励方法局限**：预定义的内在奖励（IRAT）相比 M³HF 差距大，因为无法动态识别协调失败点。

## 7. 优点

- **创新性**：首次将**多阶段、混合质量的人类自然语言反馈**在线融入 MARL，利用 LLM 作为理解接口，降低人类参与门槛。
- **方法论完整**：从数学建模（MHF-MG）到算法实现、理论鲁棒性证明，形成闭环。
- **实用性强**：仅需 5 次以内人机交互即可达到高水平，且对非专家友好。
- **消融充分**：验证了反馈解析、权重调整、多阶段迭代、与内在奖励对比等关键设计。

## 8. 不足与局限

- **环境单一**：主要实验限于 Overcooked 一类协作烹饪任务，虽有 GRF 扩展，但缺乏更多元环境（如混合合作-竞争、大规模智能体）。
- **人类反馈成本未量化**：论文定位“减少人类参与”，但仅提到最多 5 次交互，未报告实际人类标注时间或成本。
- **LLM 依赖**：反馈解析依赖 GPT-4o，存在 API 成本、延迟和潜在幻觉风险；实验未对比不同 LLM 的敏感性。
- **VLM 实验较弱**：仅测试一种 VLM（Gemini 1.5 Pro），且结论是 VLM 失败，但未尝试微调或更好模型。
- **开放性问题**：若人类持续提供低质量反馈（非偶然），性能边界如何？理论分析假设权重调整能快速抑制，但缺乏长期实验验证。
- **超参数选择未深入探讨**：权重衰减系数 \(\alpha\)、调整步长 \(\beta\) 等经验设定，未进行系统灵敏度分析。

（完）
