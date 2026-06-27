---
title: Grammar-Forced Translation of Natural Language to Temporal Logic using LLMs
title_zh: 使用LLM进行自然语言到时态逻辑的语法强制翻译
authors: "William H English, Dominic Simon, Sumit Kumar Jha, Rickard Ewetz"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=p411a7WHox"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 将自然语言翻译为强化学习中的时态逻辑规范
tldr: 该论文提出GraFT框架，利用LLM将自然语言翻译为时态逻辑（TL），核心是语法强制翻译，限制令牌预测空间以降低复杂度并提升准确性。解决了现有方法在原子命题指代和限数据下的困难。实验表明在翻译任务上优于基线，可用于人机交互中的规范生成。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1740, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1865, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1778, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1780, \"height\": 658, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1778, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1734, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1043, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 961, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 993, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 993, \"height\": 285, \"label\": \"Table\"}]"
motivation: 现有自然语言到时态逻辑翻译方法在准确性、指代消解和少量数据下表现不佳。
method: 提出GraFT框架，通过语法约束引导LLM逐步生成TL表达式，减少搜索空间。
result: 在多个数据集上显著提升了翻译准确率，并能处理指代和有限数据场景。
conclusion: GraFT为自然语言到形式逻辑转换提供了高效解决方案，有助于机器人和自主系统的规范编程。
---

## Abstract
Translating natural language (NL) into a formal language such as temporal logic (TL) is integral for human communication with robots and autonomous systems. State-of-the-art approaches decompose the task into a grounding of atomic propositions (APs) phase and a translation phase. However, existing methods struggle with accurate grounding, the existence of co-references, and learning from limited data. In this paper, we propose a framework for NL to TL translation called Grammar Forced Translation (GraFT). The framework is based on the observation that previous work solves both the grounding and translation steps by letting a language model iteratively predict tokens from its full vocabulary. In contrast, GraFT reduces the complexity of both tasks by restricting the set of valid output tokens from the full vocabulary to only a handful in each step. The solution space reduction is obtained by exploiting the unique properties of each problem. We also provide a theoretical justification for why the solution space reduction leads to more efficient learning. We evaluate the effectiveness of GraFT using the CW, GLTL, and Navi benchmarks. Compared with state-of-the-art translation approaches, it can be observed that GraFT improves the end-to-end translation accuracy by 5.49% and out-of-domain translation accuracy by 14.06% on average.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：自然语言（NL）到形式语言（如时态逻辑TL）的翻译是实现人机交互、机器人自主系统规范编程的关键。现有方法通常分为两步：原子命题（AP）接地（提取NL中的AP）和NL到TL的翻译。然而，现有技术面临三大挑战：AP接地不准确（尤其是存在共指现象时）、翻译学习依赖大量数据、端到端准确性有限（约70%）。
- **意义**：解决该问题能有效降低用户编写形式规范的门槛，推动机器人、自驾驶等系统的安全、可靠部署。本文提出GraFT框架，通过利用问题特性和TL语法限制输出令牌空间，显著提升了翻译准确率和小样本泛化能力。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将NL→TL翻译分解为AP接地（用MLM预测整数标签）和翻译（用Seq2Seq模型）；在每一步利用TL语法和AP任务特性，将LLM的预测范围从完整词表（数万）缩窄至极少数合法令牌（≤20），从而降低任务复杂度、提高学习效率。
- **关键技术细节**：
  - **AP接地（Masked Language Model）**：使用BERT（或RoBERTa、DistilBERT）对输入NL每个token预测指示变量 \(I_i\)（0=非AP，1~5=第n个AP）。输出词表仅含6个整数，极大缩小搜索空间。
  - **Grounded NL→TL翻译（Seq2Seq + Grammar Constrained Decoding）**：使用T5模型。训练时采用教师强制（teacher forcing）结合语法约束：根据上一步目标序列中的token更新TL解析器状态，仅保留当前语法状态下合法的token，将其余logit设为 \(-\infty\)。推理时同样基于模型自身输出维护语法状态，动态掩码无效令牌。
  - **理论分析**：证明了语法强制下交叉熵损失不高于标准交叉熵；梯度仅聚焦合法令牌，减少无效梯度噪声，使收敛更稳定、快速（降低方差常数 \(M\)，加速SGD）。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：三个NL-TL基准：
  - Navigation (Navi)：7079条NL，142种TL表达式
  - GLTL：11153条NL，188种TL
  - CW：2130条NL，39种TL
- **对比方法**：
  - NL2LTL（GPT-4o-mini，无AP接地）
  - NL2Spec（GPT-4o-mini，无AP接地）
  - Ungrounded Seq2Seq（T5，无AP接地）
  - NL2TL（GPT-4o-mini或GPT-4做AP接地 + T5翻译）
  - GraFT（BERT做AP接地 + T5翻译，含语法强制训练与解码）
- **评估设置**：每数据集1000个测试样本；训练数据量分500和2000；AP接地还测试了跨域迁移（仅用Navi训练，测试CW、GLTL）。
- **消融实验**：
  - AP接地：比较GPT-4o-mini/GPT-4等CLM与BERT/RoBERTa/DistilBERT等MLM的准确性。
  - 翻译：比较T5有无语法强制在不同训练数据量下的准确率。
  - 域外泛化：用两个域的数据训练，在第三个域测试（表4）。
  - 附加消融：对AP数量6~10、11~15范围的接地性能评估（附录表6、7）。

## 4. 资源与算力

- **硬件**：单台机器配置：
  - NVIDIA RTX 4070 Ti Super GPU
  - Intel i9-14900KF 32核CPU
  - 64GB RAM
- **训练参数**：AP接地模型训练3轮，学习率1e-5；翻译模型训练3轮，学习率2e-5。
- **未明确说明**：具体训练时长、模型参数量（BERT base? T5-small/base?）、总计算开销。

## 5. 实验数量与充分性

- **实验数量**：核心端到端实验（表2）涵盖3个数据集×2种数据量×6种方法，共36个结果；域外泛化实验（表4）3种训练组合×3个测试域×2种方法，共18个结果；AP接地消融（表3）6种模型×3个数据集；翻译模型消融（图5）3种模型×3个数据集×多种数据量（3×3×5≈45点）；附加消融（2个表）进一步验证AP数的影响。
- **充分性**：覆盖了主方法、消融、域外泛化，对比方法多样，可重复性高。训练测试数据划分固定，使用了统一测试集（1000例）。MLM训练仅用导航域却能在其他域良好泛化，证明了方法的有效性。
- **公平性**：所有对比方法使用相同训练数据量（500/2000），GraFT的AP接地MLM与翻译T5训练策略一致（3轮、相同lr）。

## 6. 论文的主要结论与发现

- GraFT在**所有数据集和两种数据量下均取得最高端到端准确率**（2000数据量时平均99.6%），相比NL2TL平均提升约5.49%（数据量500时）至接近满分。
- **域外泛化**显著优于基线：平均提升14.06%（最高达25.7%），说明语法强制训练有效减少了过拟合。
- **AP接地上MLM（BERT等）远优于CLM（GPT系列）**：在导航域MLM准确率近100%，而GPT-4o-mini仅82~86%；且BERT跨域保持97%以上，GPT-4o-mini跨域下降明显。
- **语法强制训练**使T5在小样本（如250、500）下准确率比标准T5高0.9%~42.1%，且随着数据增加不会出现退化（标准T5在CW上反而下降）。
- 理论证明支持：语法掩码降低交叉熵、减少梯度方差，从而加速收敛。

## 7. 优点

- **方法创新**：将任务特性（AP整数标签、TL上下文无关文法）转化为显式约束，极大减小输出空间，是“以结构换效率”的典范。
- **理论坚实**：提供数学证明（交叉熵减少、梯度聚焦），使方法有可靠保证。
- **实验全面**：跨域测试、消融、数据量变化、AP数扩展等，充分验证了方法鲁棒性和数据效率。
- **结果显著**：在小样本和跨域场景提升尤为突出，对实际应用（标注数据稀缺）极具价值。
- **实现简洁**：基于现有开源模型（BERT、T5）微调，无需定制大模型，易于复现。

## 8. 不足与局限

- **数据规模有限**：仅使用三个基准数据集，且每个域TL表达式种类偏少（CW仅39种），可能无法覆盖复杂现实场景。论文也承认需要更多数据集评估迁移性。
- **AP接地依赖整数标签**：当AP数量超过5时，指示变量方案需要扩展（附录中测试了6~15个AP，效果仍好但未说明如何扩展标签）。
- **仅测试特定模型**：AP接地仅用BERT系列，翻译仅用T5；未探索更大LLM（如Llama、GPT做翻译并语法约束）。但保持基线对比公平。
- **缺乏安全性分析**：未讨论错误翻译可能导致的安全问题，以及语法强制是否可能遮蔽合理但语料外表达。
- **计算资源未量化**：未给出训练时间、能耗等，不利于资源受限场景的判断。
- **理论分析基于特定假设**：需要真实分布满足“正确语法”假设，若目标序列包含语法外令牌（数据噪声或新语法），方法可能失效。

（完）
