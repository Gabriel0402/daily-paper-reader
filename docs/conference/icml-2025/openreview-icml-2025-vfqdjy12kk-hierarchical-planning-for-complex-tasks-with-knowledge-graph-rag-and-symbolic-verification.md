---
title: Hierarchical Planning for Complex Tasks with Knowledge Graph-RAG and Symbolic Verification
title_zh: 基于知识图谱检索增强生成与符号验证的复杂任务分层规划
authors: "Flavio Petruzzellis, Cristina Cornelio, Pietro Lio"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vfqdJy12Kk"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 神经符号规划与符号验证用于任务分解
tldr: 针对LLM机器人规划器在长期复杂任务中的不足，提出神经符号方法。结合知识图谱RAG进行分层计划生成，并通过符号验证确保分解的正确性和可执行性。在复杂任务规划实验中实现了更可靠和正确的执行序列，证明了深度融合RAG与符号验证的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vfqdjy12kk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vfqdjy12kk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vfqdjy12kk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vfqdjy12kk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vfqdjy12kk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 799, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 812, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1468, \"height\": 720, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1068, \"height\": 720, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1524, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1766, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1242, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1764, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1765, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1767, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1765, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1586, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1762, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1766, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1767, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vfqdjy12kk/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1767, \"height\": 381, \"label\": \"Table\"}]"
motivation: 大语言模型作为机器人规划器在处理长期复杂任务时存在不足。
method: 提出神经符号方法，结合知识图谱RAG进行分层计划生成，并通过符号验证确保分解正确性。
result: 在复杂任务规划中实现了更可靠和正确的执行序列。
conclusion: 深度集成知识图谱RAG和符号验证能显著提升LLM规划器的可靠性。
---

## Abstract
Large Language Models (LLMs) have shown promise as robotic planners but often struggle with long-horizon and complex tasks, especially in specialized environments requiring external knowledge. While hierarchical planning and Retrieval-Augmented Generation (RAG) address some of these challenges, they remain insufficient on their own and a deeper integration is required for achieving more reliable systems. To this end, we propose a neuro-symbolic approach that enhances LLMs-based planners with Knowledge Graph-based RAG for hierarchical plan generation. This method decomposes complex tasks into manageable subtasks, further expanded into executable atomic action sequences. To ensure formal correctness and proper decomposition, we integrate a Symbolic Validator, which also functions as a failure detector by aligning expected and observed world states. Our evaluation against baseline methods demonstrates the consistent significant advantages of integrating hierarchical planning, symbolic verification, and RAG across tasks of varying complexity and different LLMs. Additionally, our experimental setup and novel metrics not only validate our approach for complex planning but also serve as a tool for assessing LLMs' reasoning and compositional capabilities. Code available at https://github.com/corneliocristina/HVR.

---

## 论文详细总结（自动生成）

## 中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：LLM作为机器人规划器在处理长期复杂任务（如多步厨房操作）时，缺乏分层推理能力和对环境对象的细粒度知识，导致计划不可靠、错误频出。
- **背景**：已有分层规划和检索增强生成（RAG）分别部分解决了分解复杂任务和注入外部知识的问题，但单独使用仍不足。需要更深度的神经符号整合，结合符号验证机制来保证计划的正确性、可执行性以及实时错误检测。
- **总体目标**：提出一个名为 **HVR** 的神经符号系统，通过整合**分层规划**、**基于知识图谱的RAG**和**符号验证**，大幅提升LLM在复杂长期任务中的规划准确性和鲁棒性。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将复杂任务分解为高层宏动作（Macro Actions, MAs），每个宏动作再展开为原子动作序列（Atomic Actions, AAs），并利用知识图谱（KG）检索相关对象信息辅助LLM生成计划，最终通过符号验证器（基于PDDL）对计划进行形式化检查和错误纠正。
- **关键组件**：
  - **本体与动态知识图谱**：使用OntoThor本体描述厨房环境、机器人动作等；执行过程中动态更新KG（存储对象状态、事件）。
  - **知识图谱RAG**：基于任务描述从KG中检索相关对象及其属性、状态，构造子图作为LLM提示上下文。
  - **分层规划**：
    - 策略 φ：任务→宏动作序列（M-plan）。
    - 策略 π：宏动作→AA块（原子动作序列）。
    - 使用冻结的LLM生成，通过动作解析器与映射器得到标准动作。
  - **符号验证与纠正**：
    - **启发式纠正**：补充缺失的导航等动作。
    - **符号验证器**：使用PDDL预/后置条件检查计划可行性，并指出具体违反条件。
    - **LLM纠正**：基于验证器反馈，重新生成宏动作条件或AA块序列。
    - **执行时对齐**：比较预期状态与实时场景图，检测执行失败。
  - **宏动作库**：成功执行后，宏动作存入本体，支持跨机器人知识迁移与复用。

### 3. 实验设计：数据集/场景、基准、对比方法

- **模拟器与本体**：AI2Thor（3D厨房环境） + OntoThor本体。
- **任务**：共12个（表1），分为中等复杂度（T1~T6，步骤≤20，对象少）和高复杂度（T7~T12，步骤>20，对象≥3）。
- **对比基线**（5种）：
  - **HV**：分层+符号验证，无RAG（提供完整KG）。
  - **HR**：分层+RAG，无验证。
  - **VR**：验证+RAG，无分层。
  - **R**：仅RAG，无分层/验证。
  - **LLM**：仅LLM（提供完整KG）。
- **评测指标**（6个新指标）：
  - 计划生成与执行：Plan Correctness (PC)、Execution Success (ES)；
  - 计划最小性：Length Discrepancy (LD)；
  - 符号验证与纠正：Expanded Plan Verification (EPV)、Macro Plan Verification (MPV)、Atomic Action Block Verification (AABV)。
- **LLM选择**：Phi-3-mini（小型开源）和 Gemini-1.5-flash（大型闭源，免费），强调可重复性。

### 4. 资源与算力

- **未明确说明**：论文未提及使用的GPU型号、数量、训练时长（所有LLM均为冻结推理，无需训练）。只提到使用免费的LLM API或本地部署。因此读者无法知悉具体算力消耗。

### 5. 实验数量与充分性

- **实验规模**：12个任务 × 6种方法 × 2种LLM = 144组主要实验；另有T5 vs T5bis任务变体对比；以及附加的与Smart-LLM和ProgPrompt的少量对比（附录B.8）。
- **充分性**：覆盖了不同复杂度（中等/高）和不同能力LLM（小/大），并设计多种消融实验（有无RAG、有无验证、有无分层）。指标全面，从计划正确性、最小性到形式验证均有评估。
- **客观性与公平性**：
  - 所有方法使用相同的LLM、提示模板、环境设置。
  - 但未说明多次运行取平均（单次运行可能受LLM随机性影响），尽管表2中的“avg.”可能是单次结果。
  - 与SOTA比较较少，但作者解释了原因（环境不兼容、任务复杂度不匹配）。
- **结论**：实验设计总体充分，但缺乏对LLM随机性的统计处理（如多次重复均值+方差），存在一定偏差风险。

### 6. 论文的主要结论与发现

- **HVR显著优于所有基线**：在PC指标上，HVR在Gemini上平均94.19%（中等100%，高复杂88.39%），远超第二名HV（85.27%）；在Phi3上HVR也最高（59.66%）。
- **RAG对小LLM关键，分层规划对大LLM更重要**：Phi3下HR > HV，说明RAG补偿了小模型推理不足；Gemini下HV > HR，说明大模型更受益于分层分解。
- **符号验证提升形式正确性**：EPV与PC高度正相关；纠正后MPV和AABV大幅提升。
- **LLM生成计划偏长**：HVR计划长度是GT的2~3倍（Gemini约109%，Phi3约203%），纠正可能引入多余步骤。
- **执行成功率约95%**：即使计划完全正确，模拟器执行仍有5%失败，凸显模拟器与真实机器人差距。
- **LLM在开放目标任务上表现差**：如T5bis（通用“热杯水”）比T5（指定微波炉）更困难。

### 7. 优点

- **方法创新性**：首次深度整合分层规划、知识图谱RAG和符号验证，构成完整神经符号框架。
- **可重复性强**：使用免费开源LLM（Phi3）和公开模型（Gemini免费版），代码已开源。
- **指标体系全面**：提出6个新型评估指标，覆盖计划正确性、最小性、形式验证、执行成功率，有助于标准化评测。
- **知识迁移**：宏动作库允许不同机器人共享和复用计划，利于多代理协作和持续学习。
- **鲁棒性提升**：符号验证不仅事前检查，还作为实时失败检测器，增强系统适应性。
- **消融实验设计合理**：通过控制变量法清晰揭示了各组件的贡献。

### 8. 不足与局限

- **固定本体和动作空间**：需领域专家手动定义，限制了向新环境/任务的泛化。
- **提示敏感性**：LLM对提示措辞敏感，虽未深入分析，但可能影响实际部署稳定性。
- **自然语言交互低效**：当前使用自然语言作为KG与LLM间的接口，未来可采用子符号或嵌入表示提高效率。
- **仅支持线性计划**：不支持部分有序/并行执行，不适合多代理或需要分支的任务。
- **纠错机制孤立**：不同层级（宏、原子）的纠错独立进行，未考虑跨层级依赖，可能遗漏全局最优修正。
- **模拟器局限**：AI2Thor执行可靠性仅95%，可能掩盖部分规划错误，现实世界鲁棒性需进一步验证。
- **实验统计不充分**：未提供多次运行的标准差或置信区间，随机性对结果影响不明。
- **与SOTA比较不足**：尽管作者说明了原因，但缺乏与规划方法（如PDDL求解器、其他神经符号系统）的直接对比，削弱了说服力。

（完）
