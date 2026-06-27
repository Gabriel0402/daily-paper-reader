---
title: "NADER: Neural Architecture Design via Multi-Agent Collaboration"
title_zh: NADER：基于多智能体协作的神经架构设计
authors: "Yang, Zekang, Zeng, Wang, Jin, Sheng, Qian, Chen, Luo, Ping, Liu, Wentao"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Yang_NADER_Neural_Architecture_Design_via_Multi-Agent_Collaboration_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 6.0
evidence: 多智能体协作与LLM用于神经架构设计
tldr: 现有神经架构搜索方法受限于预定义搜索空间，可能遗漏关键架构。NADER提出基于LLM的多智能体协作框架，通过团队专业化智能体迭代修改基础架构，并具备从过去经验中学习的能力。实验表明该方法能有效发现高性能架构，为多智能体与LLM结合提供了新思路。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-nader-neural-architecture-design-via-multi-agent-collaboration-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-nader-neural-architecture-design-via-multi-agent-collaboration-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1694, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-nader-neural-architecture-design-via-multi-agent-collaboration-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yang-nader-neural-architecture-design-via-multi-agent-collaboration-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 700, \"height\": 702, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-nader-neural-architecture-design-via-multi-agent-collaboration-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1794, \"height\": 1197, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-nader-neural-architecture-design-via-multi-agent-collaboration-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yang-nader-neural-architecture-design-via-multi-agent-collaboration-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 881, \"height\": 399, \"label\": \"Table\"}]"
motivation: 现有NAS方法搜索空间固定，可能错过最优架构。
method: 将架构设计建模为LLM多智能体协作问题，团队智能体迭代修改架构。
result: NADER能发现超越基线的高效架构。
conclusion: 多智能体LLM协作可提升神经架构设计的探索能力。
---

## Abstract
Designing effective neural architectures poses a significant challenge in deep learning. While Neural Architecture Search (NAS) automates the search for optimal architectures, existing methods are often constrained by predetermined search spaces and may miss critical neural architectures. In this paper, we introduce NADER (Neural Architecture Design via multi-agEnt collaboRation), a novel framework that formulates neural architecture design (NAD) as a LLM-based multi-agent collaboration problem. NADER employs a team of specialized agents to enhance a base architecture through iterative modification. Current LLM-based NAD methods typically operate independently, lacking the ability to learn from past experiences, which results in repeated mistakes and inefficient exploration. To address this issue, we propose the Reflector, which effectively learns from immediate feedback and long-term experiences. Additionally, unlike previous LLM-based methods that use code to represent neural architectures, we utilize a graph-based representation. This approach allows agents to focus on design aspects without being distracted by coding. We demonstrate the effectiveness of NADER in discovering high-performing architectures beyond predetermined search spaces through extensive experiments on benchmark tasks, showcasing its advantages over state-of-the-art methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统神经架构搜索（NAS）方法依赖专家预定义的搜索空间，无法发现真正新颖的架构；而现有基于LLM的神经架构设计（NAD）方法通常独立运行，无法从过去经验中学习，导致重复错误和低效探索。
- **整体含义**：本文提出NADER，将神经架构设计建模为基于LLM的多智能体协作问题，通过团队协作和反思机制，实现超越预定义搜索空间的高效架构发现。

## 2. 论文提出的方法论

### 核心思想
- 将NAD范式化为多智能体协作：研究团队（Reader + Proposer）负责提出改进方案，开发团队（Modifier + Reflector）负责实现与验证。
- 引入**图表示的神经网络架构**（DAG），避免代码实现细节干扰。
- 引入**Reflector**智能体，既能从即时反馈（LIF）中学习，也能从历史设计经验（LDE）中积累知识。

### 关键技术细节
- **Reader**：自动从学术论文中提取与架构设计相关的知识，存入向量数据库。
- **Proposer**：基于网络修改树（记录每次修改历史与性能），结合Reader知识池和Reflector提供的经验，选择最有潜力的候选架构和修改建议。
- **Modifier**：分层次实现修改（先设计cell block，再设计stem/downsample块），使用图表示并检测同构性以避免重复训练。
- **Reflector**：
  - LIF：使用计算图流验证工具检查架构可执行性，与Modifier多轮对话修正错误。
  - LDE：将历史记录（成功/失败/失败转成功）分类存储，并为每次修改检索5条相关经验作为上下文。
- **算法流程**：初始化基础架构 → 循环（Proposer生成提案 → Reflector检索经验 → Modifier生成新架构 → 验证正确性 → 训练评估性能 → 更新修改树和历史记录），直到生成足够数量的架构。

## 3. 实验设计

### 数据集与场景
- **NAS-Bench-201**基准：CIFAR-10、CIFAR-100、ImageNet16-120。
- **自建NAD Benchmark**：5种基础模块（ResNet base/bottleneck、GoogLeNet、ConvNeXt、SE-ResNet），每种模块配10个宏观+10个微观修改建议，共100个测试样本。

### 对比方法
- **NAS方法**：随机搜索（RS, RSPS）、进化方法（REA）、强化学习（REINFORCE, ENAS）、HPO（BOHB）、可微分方法（DARTS, PC-DARTS, GDAS等）、LLM方法（GENIUS, LLMatic）。
- **NAD方法**：LeMo-NADe（使用Gemini和GPT4-Turbo）。

### 公平性约束
- 保证NADER生成的架构与NAS-Bench-201具有相同宏观骨架。
- 限制参数量（≤1.5M）和FLOPs（CIFAR≤0.2G，ImageNet16-120≤0.05G）。
- 训练超参数与NAS-Bench-201完全一致。

## 4. 资源与算力

- 论文**未明确说明GPU型号、数量或训练时长**。
- 在4.4节大规模实验（CIFAR-100，生成500个架构）中报告了**计算开销**：输入token 5,371K，输出token 987K，总计花费$23（按GPT-4o价格：$2.50/M输入，$10.00/M输出），平均每个架构成本$0.046。
- 说明该方法在推理阶段（LLM调用）成本可控，但未报告训练这些架构所需的GPU算力。

## 5. 实验数量与充分性

### 实验组别
- **主实验（Table 1）**：在三个数据集上对比多种NAS和NAD方法，NADER使用随机初始化和ResNet初始化，分别报告5个和10个架构的设计结果，每个结果3次重复取均值。
- **消融实验**：
  - Table 2：研究团队（Reader和Proposer）的消融，在三个数据集上各5次迭代。
  - Table 3：开发团队（图表示、LIF、LDE）的消融，在自建NAD Benchmark的100个样本上评估可执行性(E)、质量(Q)、成功率(SR)、Token数。
- **大规模实验（图4）**：在CIFAR-100上生成500个架构，展示优化路径和最终性能（76.0%测试准确率）。

### 充分性与客观性
- 实验设计较为充分，涵盖了NAS和NAD两大范式、多种类型算法。
- 消融实验系统性地验证了各组件的贡献。
- 公平性约束和重复实验增加了可信度。
- **不足**：NAD Benchmark 为自建，可能引入主观偏差；未在更大规模数据集（如ImageNet）上验证；对比的LeMo-NADe只报告了30次试验的结果，而NADER在5或10次试验下就超越，但未说明LeMo-NADe在更多试验下的表现。

## 6. 论文的主要结论与发现

- NADER在三个数据集上均设计出超越NAS-Bench-201最优性能（Optimal）的架构，验证了突破预定义搜索空间的价值。
- 即使从随机网络开始，仅通过5-10次迭代即可达到或超过传统NAS方法（500次迭代）的性能。
- 图表示相比代码表示能显著提高架构修改的成功率并减少Token消耗。
- Reader和Proposer对最终性能贡献显著，尤其是在ImageNet16-120数据集上。
- LIF和LDE均能提升可执行性和质量，其中LDE对微观修改提升尤其明显（成功率从0.62提升至0.88）。
- 在CIFAR-100大规模实验中，从ResNet出发经过500次迭代获得76.0%测试精度，比初始提升5.14%。

## 7. 优点

- **创新性**：将多智能体协作、反思学习、图表示引入NAD，突破了传统NAS的空间限制。
- **高效性**：仅需少量试验（5-10次）即可发现高性能架构，成本极低（$0.046/架构）。
- **系统设计完整**：Reader获取前沿文献知识，Proposer智能选候选，Reflector累积经验，形成闭环迭代。
- **图表示的巧妙运用**：避免LLM被代码细节分散注意力，同时支持同构检测和更紧凑的表示。
- **消融实验全面**：充分验证每个组件的贡献，实验设计公平（约束计算资源、训练设置一致）。

## 8. 不足与局限

- **实验覆盖有限**：仅在NAS-Bench-201的三个中等规模数据集上验证，未在ImageNet大规模图像分类或其他领域（如NLP、目标检测）上测试。
- **NAD Benchmark自建**：100个样本由作者手动生成和审核，可能存在主观性，且样本量较小。
- **对比局限性**：LeMo-NADe报告结果仅30次试验，NADER在5-10次试验下对比，但未给出LeMo-NADe在相同试验次数下的结果。
- **算力信息缺失**：未报告训练新架构所需的GPU型号、数量和总时长，难以评估实际计算成本。
- **LLM依赖**：方法依赖GPT-4o等商用模型，可复现性受限于API可用性和成本。
- **大规模实验深度不足**：虽然展示了500次迭代的结果，但未深入分析架构创新点（如具体结构变化、与现有SOTA的差距）。

（完）
