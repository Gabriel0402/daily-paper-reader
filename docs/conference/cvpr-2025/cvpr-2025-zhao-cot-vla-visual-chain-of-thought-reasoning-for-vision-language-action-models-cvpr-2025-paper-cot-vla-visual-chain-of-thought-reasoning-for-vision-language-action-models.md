---
title: "CoT-VLA: Visual Chain-of-Thought Reasoning for Vision-Language-Action Models"
title_zh: CoT-VLA：视觉语言动作模型的视觉思维链推理
authors: "Zhao, Qingqing, Lu, Yao, Kim, Moo Jin, Fu, Zipeng, Zhang, Zhuoyang, Wu, Yecheng, Li, Zhaoshuo, Ma, Qianli, Han, Song, Finn, Chelsea, Handa, Ankur, Lin, Tsung-Yi, Wetzstein, Gordon, Liu, Ming-Yu, Xiang, Donglai"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhao_CoT-VLA_Visual_Chain-of-Thought_Reasoning_for_Vision-Language-Action_Models_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 9.0
evidence: 视觉-语言-动作模型结合视觉思维链
tldr: 现有VLA模型缺乏中间推理步骤，难以处理复杂操作任务。本文提出CoT-VLA，通过自回归预测未来图像帧作为视觉目标，在执行动作前引入显式视觉思维链推理。在多个机器人操作基准上，该方法显著提升了零样本泛化和任务成功率，为VLA模型赋予时序规划能力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1798, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 655, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1811, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1746, \"height\": 1196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 632, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1565, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 875, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhao-cot-vla-visual-chain-of-thought-reasoning-for-vision-language-action-models-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 195, \"label\": \"Table\"}]"
motivation: 现有VLA模型缺乏中间推理和时序规划能力。
method: 在VLA中引入视觉思维链，通过预测未来图像帧作为目标再生成动作。
result: 显著提升复杂操作任务的泛化性和成功率。
conclusion: 视觉思维链推理有效增强了VLA的时序规划能力。
---

## Abstract
Vision-language-action models (VLAs) have shown potential in leveraging pretrained vision-language models and diverse robot demonstrations for learning generalizable sensorimotor control. While this paradigm effectively utilizes large-scale data from both robotic and non-robotic sources, current VLAs primarily focus on direct input--output mappings, lacking the intermediate reasoning steps crucial for complex manipulation tasks. As a result, existing VLAs lack temporal planning or reasoning capabilities. In this paper, we introduce a method that incorporates explicit visual chain-of-thought (CoT) reasoning into vision-language-action models (VLAs) by predicting future image frames autoregressively as visual goals before generating a short action sequence to achieve these goals. We introduce CoT-VLA, a state-of-the-art 7B VLA that can understand and generate visual and action tokens. Our experimental results demonstrate that CoT-VLA achieves strong performance, outperforming the state-of-the-art VLA model by 17% in real-world manipulation tasks and 6% in simulation benchmarks. Videos are available at: https://cot-vla.github.io/.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的视觉-语言-动作模型（VLA）直接学习从观测到动作的映射，缺乏中间推理步骤，导致无法处理需要时序规划和复杂操作的机器人任务。
- **背景**：语言领域中的思维链（Chain-of-Thought, CoT）提示能够提升大模型的逐步推理能力。将此概念引入机器人领域，可以通过中间表示（如语言描述、关键点、边界框）来显式地推理下一步状态，但目前这些表示需要额外预处理或缺少与动作生成的紧密耦合。
- **核心问题**：能否利用子目标图像作为视觉思维链的中间步骤，在生成动作之前先“视觉地思考”未来状态，从而提升VLA的推理能力和任务成功率？

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- **视觉链式推理（Visual CoT）**：在VLA中引入显式的视觉推理步骤——先自回归地预测一个未来帧（子目标图像），再基于当前观测和该子目标生成一组短动作序列。
- 这样既利用了机器人演示数据中的自然中间状态（子目标），又能通过无动作标注的视频数据进行预训练，提升视觉推理能力。

### 关键技术细节
- **基座模型**：选用VILA-U（7B参数），该模型能够理解和生成图像与文本，通过残差量化将图像编码为离散token（16×16×4 tokens）。
- **训练数据**：
  - 机器人演示数据 \(D_r\)：Open X-Embodiment子集（单臂、7自由度、第三视角）。
  - 无动作视频数据 \(D_v\)：EPIC-KITCHENS-100、Something-Something V2。
- **训练目标**：
  1. **子目标图像生成**：给定语言指令 \(l\) 和当前观测 \(s_t\)，预测 \(n\) 帧后的图像 \(s_{t+n}\)（自回归，使用因果注意力）。
  2. **动作生成**：给定 \(l\)、\(s_t\) 和 \(s_{t+n}\)，预测长度为 \(m\) 的动作序列 \([a_t, ..., a_{t+m}]\)（使用全注意力，动作维度独立离散化为256个bin）。
  损失函数为 \(L = L_{\text{action}} + L_{\text{visual}}\)。
- **混合注意力机制**：图像/文本生成使用因果注意力，动作预测使用全注意力（允许动作token之间交互）。
- **动作分块（Action Chunking）**：一次预测多个动作，减少推理频率并与完整注意力配合。
- **测试时闭环控制**：算法流程如Algorithm 1所示——循环生成子目标图像→生成动作序列→执行→更新观测。

## 3. 实验设计：数据集/场景、benchmark、对比方法

| 实验平台 | 数据集/场景                                  | Benchmark / 评价协议                                      | 对比方法                                                                 |
|----------|----------------------------------------------|-----------------------------------------------------------|--------------------------------------------------------------------------|
| LIBERO 仿真 | LIBERO-Spatial, Object, Goal, Long (各10任务, 50演示) | 每个种子500回合, 3个种子, 报告平均成功率与标准误差        | Diffusion Policy, Octo (fine-tuned), OpenVLA (fine-tuned)              |
| Bridge-V2 真实机器人 | WidowX臂, 45k语言标注轨迹                     | 4个泛化类别：视觉、运动、语义、语言接地；每个类别10次尝试 | SUSIE, Octo, OpenVLA                                                   |
| Franka-Tabletop 真实机器人 | 6个任务（3个窄领域单指令 + 3个多指令）, 10~150演示 | 每个任务多次运行（具体未明确但见于图4）                  | Diffusion Policy, Octo (fine-tuned), OpenVLA (fine-tuned)              |

- **总体**：在仿真（LIBERO）、真实机器人（Bridge-V2、Franka-Tabletop）上评估，对比了基于扩散的策略、两种通用VLA（Octo、OpenVLA）以及两阶段方法SUSIE。

## 4. 资源与算力

论文中明确说明了**使用NVIDIA GPU**，但未给出具体型号、数量和训练时长。文中提到“current computational constraints limit its ability to achieve visual-reasoning generalization”，暗示算力有限。预训练和微调均在NVIDIA的集群上进行，但细节未披露。

## 5. 实验数量与充分性

- **LIBERO**：4个task suite × 3个种子 × 500 episodes = 6000次评估，覆盖空间、物体、目标、长时任务。
- **Bridge-V2**：4个泛化类别 × 10次尝试 = 40次评估，但仅进行了单次测试（无标准误差报告）。
- **Franka-Tabletop**：6个任务，每个任务多次（图中显示具体次数，但论文未对每任务次数说明）。
- **消融实验**：在LIBERO-Spatial和LIBERO-Goal上评估了动作分块、混合注意力、视觉CoT的贡献；在Franka-Tabletop上评估了预训练阶段的效果；还设计了“Better Visual Reasoning Helps”实验（使用真实目标图像 vs 生成目标图像，2个长时任务各5次尝试）。
- **充分性**：覆盖仿真和多个真实机器人平台，对比了领先基线，消融实验设计合理。但Bridge-V2的样本量较小（每类10次），且未报告置信区间；Franka-Tabletop的任务数量有限。总体实验设计**较为充分，但存在小样本风险**。

## 6. 论文的主要结论与发现

1. **视觉CoT显著提升VLA性能**：在LIBERO上CoT-VLA平均成功率81.13%，比现有最佳VLA（OpenVLA 76.5%）高出约4.6个百分点；在Franka-Tabletop上平均表现优于Diffusion Policy、Octo和OpenVLA。
2. **动作分块+混合注意力+视觉CoT逐层提升**：消融实验显示每一步改进均有效，视觉CoT带来最大增益。
3. **预训练阶段加入无动作视频数据提升性能**：在Franka-Tabletop上，使用预训练（OpenX+视频）比直接微调VILA-U绝对提升25.1个百分点（从53.7%到78.8%）。
4. **更好的视觉推理直接改善任务成功率**：在模外任务上，使用真实目标图像比生成目标图像成功率提升40%，说明提升子目标生成质量可转化为实际性能提升。
5. **CoT-VLA在指令跟随和语言接地方面表现更强**，特别是在LIBERO中避免了因视觉相似而忽视指令的错误。

## 7. 优点

- **新颖的视觉CoT范式**：首次将子目标图像生成作为VLA的中间推理步骤，可解释性强且无需额外标注。
- **充分利用无动作视频**：通过视觉CoT解耦了视觉推理和动作生成，因此能利用海量无动作视频数据预训练，缓解机器人数据稀缺问题。
- **混合注意力机制**：动作全注意力优于因果注意力，提升了动作序列的协调性。
- **综合实验验证**：在仿真和两种真实机器人平台上评估，对比了多种主流方法，消融实验充分。
- **开源与可复现**：提供视频网站和论文，模型可基于公开代码构建。

## 8. 不足与局限

- **推理速度慢**：生成子目标图像需要256个token，导致比直接动作生成慢约7倍。虽然动作分块和并行解码可缓解，但图像生成仍是瓶颈。
- **图像质量有限**：自回归图像生成质量低于扩散模型，限制了视觉推理的精度，进而影响动作成功率。
- **动作分块的跳跃问题**：相邻动作块之间可能不连续，缺乏高频反馈，可通过时域平滑或逐步预测改进。
- **泛化能力受限**：在全新、模外任务上（如长时组合任务），子目标生成质量不足，导致成功率大幅下降（20%→60%），表明视觉推理的泛化仍依赖大规模视频生成模型。
- **实验覆盖**：Bridge-V2的样本量较小（每类10次），Franka-Tabletop的任务数有限，可能低估方法的变异性；未报告置信区间或统计检验。
- **算力资源未透明**：没有提供训练所需的GPU型号、数量和时间，不利于复现和比较效率。

（完）
