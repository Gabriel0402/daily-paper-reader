---
title: "RoboGround: Robotic Manipulation with Grounded Vision-Language Priors"
title_zh: RoboGround：基于接地视觉语言先验的机器人操作
authors: "Huang, Haifeng, Chen, Xinyi, Chen, Yilun, Li, Hao, Han, Xiaoshen, Wang, Zehan, Wang, Tai, Pang, Jiangmiao, Zhao, Zhou"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Huang_RoboGround_Robotic_Manipulation_with_Grounded_Vision-Language_Priors_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 利用视觉语言模型先验将grounding掩码作为机器人操作的中间表示
tldr: 机器人操作中策略泛化依赖于有效的中间表示。RoboGround探索将分割掩码作为中间表示，利用大规模视觉语言模型在grounding数据上预训练的先验，同时提供目标位置、形状和尺寸信息。该方法引导策略网络实现精确操作，并在未见物体和场景上展现出强泛化能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 817, \"height\": 986, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1709, \"height\": 684, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1807, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 872, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 870, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-huang-roboground-robotic-manipulation-with-grounded-vision-language-priors-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 699, \"height\": 222, \"label\": \"Table\"}]"
motivation: 机器人操作策略需要具有泛化能力的中间表示，现有方法缺乏利用接地掩码作为先验。
method: 将视觉语言模型生成的接地掩码作为中间表示，引导策略网络进行物体操作。
result: 在多个操作任务上实现高成功率，且在未见物体和布局下保持强泛化。
conclusion: 接地掩码是一种有效的机器人操作中间表示，可充分利用VLM先验知识。
---

## Abstract
Recent advancements in robotic manipulation have highlighted the potential of intermediate representations for improving policy generalization. In this work, we explore grounding masks as an effective intermediate representation, balancing two key advantages: (1) effective spatial guidance that specifies target objects and placement areas while also conveying information about object shape and size, and (2) broad generalization potential driven by large-scale vision-language models pretrained on diverse grounding datasets. We introduce \method, a grounding-aware robotic manipulation policy that leverages grounding masks as an intermediate representation to guide policy networks in object manipulation tasks. To further explore and enhance generalization, we propose an automated pipeline for generating large-scale, simulated data with a diverse set of objects and instructions. Extensive experiments show the value of our dataset and the effectiveness of grounding masks as intermediate guidance, significantly enhancing the generalization abilities of robot policies.

---

## 论文详细总结（自动生成）

# 论文结构化总结：RoboGround: Robotic Manipulation with Grounded Vision-Language Priors

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：机器人操作策略的泛化能力不足。现有中间表示方法要么粗粒度（如语言指令）缺乏空间精度，要么细粒度（如点流、目标图像）需要大量训练资源和数据，难以平衡。
- **动机**：探索一种能同时提供有效空间引导（指定目标物体和放置区域、传达形状和尺寸）并具备广泛泛化潜力的中间表示。
- **核心思想**：利用大规模视觉语言模型（VLM）在多样化 grounding 数据集上预训练的先验知识，生成像素级**接地掩码（grounding masks）**，作为连接高层指令和低层动作的中间桥梁，提升策略在未见物体、场景和指令下的泛化能力。

## 2. 方法论
### 2.1 核心架构：ROBO GROUND
- **整体流程**：输入图像观测 + 语言指令 → **接地 VLM** 生成目标物体掩码 \(M_o\) 和放置区域掩码 \(M_p\) → **接地策略网络** 利用掩码引导预测机器人动作。
- **接地 VLM（基于 GLaMM 微调）**：
  - 图像经 CLIP 视觉编码器 → MLP 投影 → LLM 处理指令 → 输出含 `<SEG>` 标记的文本。
  - 通过 SAM 编码器 + SAM 解码器结构，从 `<SEG>` 标记嵌入解码出像素级掩码：\(M = D(f_s(F_{seg}), E(x_v))\)。
  - 微调损失：自回归交叉熵（文本生成）+ 逐像素 BCE + DICE（分割）。
- **接地策略网络（基于 GR-1 改进）**：
  - **通道级融合**：将掩码 \(M_o, M_p\) 与图像 \(x_v\) 通道拼接，经线性层投影回 3 通道，再输入 ViTMAE 编码器提取视觉特征 \(Z_v\)。
  - **接地感知器（Grounded Perceiver）**：引入三组可学习查询令牌（全局查询、目标物体查询、放置区域查询），在交叉注意力中通过掩码填充操作将注意力约束在掩码区域内，输出 3×k 个视觉令牌，保留关键空间信息。
  - **动作预测**：将历史 N 步的视觉令牌、CLIP 文本令牌、机器人状态令牌和可学习动作令牌聚合，输入 Transformer 解码器，预测下一步 arm 动作（Smooth-L1 损失）和 gripper 动作（BCE 损失）。
- **推理简化**：掩码仅在每轮任务开始时由 VLM 生成一次，后续策略网络复用，适用于单轮静态操作。

## 3. 实验设计
### 3.1 数据集与环境
- **仿真环境**：基于 RoboCasa 搭建，利用其自动化场景生成管线创建多样化布局和纹理。
- **训练数据**：
  - 原始 RoboCasa 66K 演示（简单任务）。
  - 自动生成管道产出 **24K 演示 + 112K 指令**，覆盖 176 类共 3,526 个物体，指令分为三类：外观指令、空间指令、常识指令。
  - 场景复杂化：引入大量干扰物体（从 Objaverse 中精选 1,017 个桌面物体）。
- **测试集**：每类指令和基础技能各 400 个样本（主实验）；零样本测试中预留 30 类 597 物体作为未见类别，并每类剔除 1/4 物体作为未见实例。

### 3.2 对比基线
- **ACT** (Zhao et al., 2023)：基于条件 VAE 的 Transformer 策略，无语言输入。
- **BC-Transformer** (Mandlekar et al., 2021)：标准行为克隆 Transformer，通过 FiLM 融合 CLIP 语言特征。
- **GR-1** (Wu et al., 2023)：GPT 风格模型，复现版无大规模预训练和图像预测。

### 3.3 评估指标
- **Pick-and-Place 任务**：接触率 (%) / 成功率 (%)。
- **基础技能**（开门/关、按按钮、转杠杆、扭旋钮）：成功率 (%)。

## 4. 资源与算力
- 论文明确指出：完整训练和评估在 **8 张 NVIDIA 4090 GPU** 上需要数天时间。
- 未给出精确训练时长或 VLM 微调的 GPU 配置。

## 5. 实验数量与充分性
- **主实验**（表 1）：4 种方法在 5 种任务（简单 pick-and-place + 三种复杂指令 + 基础技能组合）上对比，共 20 个条件。
- **零样本评估**（表 2）：在未见实例和未见类别上各 4 种指令，共 8 个条件，对比有/无掩码。
- **消融实验**（表 3-6）：
  - 训练数据（原数据 vs 新数据 vs 两者结合）和掩码类型（无/预测/GT）— 7 组条件。
  - 掩码融入模块（通道拼接 vs 接地感知器）— 4 组条件。
  - 接地表示类型（点/边界框/掩码）— 6 组条件。
  - 接地 VLM 微调策略（零样本/仿真微调/联合微调）— 3 组条件。
- **充分性**：实验覆盖了多种指令类型、物体分布、未见难度和模块设计，对比基线标准且广泛，消融设计合理。但**缺少真实世界实验**，所有评估均在仿真中进行，这限制了结论的泛化信心。

## 6. 主要结论与发现
- 接地掩码作为中间表示能显著提升机器人策略的泛化能力，尤其在复杂指令（外观、空间、常识）和零样本场景下，性能提升可达 **100% 相对改进**（如从 6.8% 提升至 30.5%）。
- 新数据集的高场景复杂度和指令多样性对模型泛化至关重要：仅用原始数据时，掩码提升有限；加入新数据后掩码优势大幅显现。
- 通道拼接和接地感知器两种融合方式均有效，联合使用效果最佳；掩码优于点或边界框表示。
- 接地 VLM 需在仿真数据上微调才能可靠跟随指令，原始零样本表现差（mIoU 13.2），微调后提升至 48.2。

## 7. 优点
- **创新性**：首次系统性地将像素级接地掩码作为机器人操作的中间表示，充分利用 VLM 在开放世界 grounding 上的先验知识。
- **平衡性**：在空间精度（形状/尺寸）和泛化潜力（依托大规模预训练）之间取得良好平衡，优于粗粒度语言和细粒度点流/图像。
- **数据工程**：提出高质量自动化数据生成管道，大幅提升指令多样性和场景复杂性，为训练接地感知策略提供基础。
- **模块化设计**：接地 VLM 与策略网络可独立微调或替换，便于未来扩展（如更换更强 VLM 或动作网络）。
- **充分消融**：逐个变量分析掩码表示、融合方式、训练数据的影响，结果可信。

## 8. 不足与局限
- **仅仿真验证**：所有实验在 RoboCasa 仿真环境中进行，未迁移到真实机器人平台，真实场景下的光照、纹理、传感器噪声等未考虑。
- **接触-成功差距**：模型接触率远高于成功率（如外观任务接触率 78.5% vs 成功率 30.5%），表明抓取位姿学习不精确，需集成专用抓取网络。
- **掩码假设静态**：推理时仅生成一次掩码，假设目标物体在被抓取前位置不变，不适合动态场景或长 Horizon 任务。
- **VLM 微调依赖仿真数据**：虽然缓解了零样本问题，但仿真数据与真实数据分布差异可能导致域偏移；联合微调原 VLM 数据仅带来微小提升（mIoU 45.5→48.2）。
- **计算成本**：VLM 生成掩码涉及较大模型（GLaMM），推理延时未报告，可能影响实时性。
- **数据集特定**：新数据集中于 pick-and-place 任务，基础技能（开门、按钮等）未扩展指令多样性，这些任务上优势较小（如表 1 中基础技能成功率仅比 GR-1 高约 5-15 个百分点）。

（完）
