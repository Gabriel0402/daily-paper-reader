---
title: Navigation World Models
title_zh: 导航世界模型
authors: "Bar, Amir, Zhou, Gaoyue, Tran, Danny, Darrell, Trevor, LeCun, Yann"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Bar_Navigation_World_Models_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 导航世界模型，具备视觉运动规划能力
tldr: 现有导航策略依赖固定行为，难以自适应约束。本文提出导航世界模型（NWM），利用条件扩散Transformer从第一人称视频中学习环境动态，能够通过模拟未来观测并评估目标达成度来规划轨迹，在规划成功率上超越传统方法。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1800, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 645, \"height\": 1047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 876, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1812, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 848, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1803, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1798, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 858, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 863, \"height\": 302, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 878, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 683, \"height\": 108, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 730, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 797, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-bar-navigation-world-models-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1662, \"height\": 165, \"label\": \"Table\"}]"
motivation: 现有导航策略行为固定，无法动态融入约束。
method: 使用条件扩散Transformer（CDiT）训练预测未来观测的世界模型，结合规划约束生成导航轨迹。
result: 在多个导航任务中实现从零规划，并优于监督策略。
conclusion: NWM为机器人导航提供了灵活、可泛化的规划框架。
---

## Abstract
Navigation is a fundamental skill of agents with visual-motor capabilities. We introduce a Navigation World Model (NWM), a controllable video generation model that predicts future visual observations based on past observations and navigation actions. To capture complex environment dynamics, NWM employs a Conditional Diffusion Transformer (CDiT), trained on a diverse collection of egocentric videos of both human and robotic agents, and scaled up to 1 billion parameters. In familiar environments, NWM can plan navigation trajectories by simulating them and evaluating whether they achieve the desired goal. Unlike supervised navigation policies with fixed behavior, NWM can dynamically incorporate constraints during planning. Experiments demonstrate its effectiveness in planning trajectories from scratch or by ranking trajectories sampled from an external policy. Furthermore, NWM leverages its learned visual priors to imagine trajectories in unfamiliar environments from a single input image, making it a flexible and powerful tool for next-generation navigation systems.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）
- **核心问题**：现有的机器人导航策略（如NoMaD、GNM）是“硬编码”的监督模型，训练后难以动态融入新约束（如“禁止左转”），也无法为困难问题动态分配更多计算资源。此外，它们缺乏像人类那样通过想象未来轨迹来规划的能力。
- **研究动机**：设计一种可泛化、可灵活调整的导航世界模型，能够通过自回归预测未来视觉观测来模拟轨迹，并根据目标与约束自动规划或优化外部策略的轨迹。
- **整体含义**：NWM（Navigation World Model）是一种可控视频生成模型，能够利用大量第一人称视频（包括机器人和人类）学习环境动态，从而在已知环境中进行高效规划，并能在未知环境中凭借视觉先验进行想象和预测，为下一代导航系统提供灵活工具。

### 方法：核心思想、关键技术细节
- **核心思想**：将导航问题转化为世界模型的序列预测问题。给定历史图像和动作序列，模型通过扩散过程预测未来的视觉状态（图像潜在表示），再解码为像素，从而实现对轨迹的模拟和评估。
- **关键技术细节**：
  - **条件扩散Transformer（CDiT）**：一种高效的Transformer架构。与标准DiT（对所有上下文帧做自注意力，复杂度O(m²n²d)）不同，CDiT只对当前待去噪帧做自注意力，对历史帧做交叉注意力，复杂度为O(mn²d)，随帧数线性增长。条件信号（动作、时间偏移、扩散步长）通过AdaIN层注入。
  - **模型公式**：状态由VAE编码器得到潜在表示\( s_t = \text{enc}(x_t) \)，世界模型\( F_\theta(s_{t+1} | s_t, a_t) \)通过扩散过程预测下一潜在状态。动作\( a_t = (u, \omega, k) \)包含平移、旋转和时间偏移\( k \)（可在±16秒内随机采样）。
  - **训练目标**：最小化预测噪声与真实噪声的MSE，并加上变分下界损失。
  - **规划方法**：使用Model Predictive Control (MPC)框架，通过交叉熵方法优化动作序列，最小化能量函数\( E = -\text{sim}(s_T, s_{\text{goal}}) + \text{惩罚项} \)；或用于对外部策略采样的轨迹进行排序。
- **算法流程**：  
  1. 给定初始观测和目标图像，编码为潜变量。  
  2. 随机初始化一组动作序列（或从外部策略采样）。  
  3. 使用NWM自回归地生成未来潜变量序列，解码最后一帧。  
  4. 计算最后一帧与目标图像之间的感知相似度（如LPIPS），加上约束惩罚。  
  5. 通过交叉熵方法迭代更新动作序列，最小化能量函数。  
  6. 选择最优动作序列执行或返回排序后的最佳轨迹。

### 实验设计
- **数据集与场景**：
  - **有标注数据集**：SCAND（社交合规导航）、TartanDrive（越野驾驶）、RECON（开放世界导航）、HuRoN（社交交互）。
  - **无标注数据集**：Ego4D（仅时间偏移作为动作）。
  - **未知环境评估**：GO Stanford（用于测试泛化）。
- **基准方法**：
  - DIAMOND（基于UNet的扩散世界模型）。
  - GNM（通用导航模型，全连接轨迹预测网络）。
  - NoMaD（基于扩散策略的导航模型）。
- **评估指标**：
  - 轨迹精度：ATE（绝对轨迹误差）、RPE（相对位姿误差）。
  - 感知相似度：LPIPS、DreamSim、PSNR。
  - 视频生成质量：FID、FVD。

### 资源与算力
- **算力配置**：XL规模（1B参数）的模型在**8台H100机器上训练，每台8个GPU**，共计64块H100 GPU。训练使用AdamW优化器，学习率8e-5，总批量大小1024，每样本4个目标，有效批量4096。文中未明确训练总时长。

### 实验数量与充分性
- **实验组数**：
  - **消融实验**：模型规模与CDiT vs DiT（图5）、目标数量（1/2/4，表1）、上下文帧数（1/2/4，表1）、时间与动作条件（表1）。
  - **视频预测与合成**：与DIAMOND对比不同时间跨度（1-16秒，图4），FVD对比（图6）。
  - **规划实验**：独立规划（表2）、带约束规划（表3）、外部策略排序（表2）。
  - **未知环境泛化**：在GO Stanford上的预测对比（表4），以及定性示例（图8）。
- **充分性**：覆盖了已知环境规划、约束规划、排序、未知环境泛化等多个维度，消融实验完整。但未知环境只测试了一个数据集（GO Stanford），且仅评估了4秒预测，缺乏长期规划实验。总体上实验设计是合理且较为充分的，但泛化性验证稍显不足。

### 主要结论与发现
1. **NWM在已知环境中可独立进行有效规划**：在RECON数据集上，NWM独立规划的ATE（1.13）和RPE（0.35）均优于GNM（1.87/0.73）和NoMaD（1.93/0.52）。
2. **动态约束规划可行**：在左转优先、直行后前进等约束下，NWM能成功规划轨迹，与无约束基线性能差距很小。
3. **NWM可提升外部策略**：对NoMaD采样的32条轨迹使用NWM排序，ATE（1.78）和RPE（0.48）均优于原生NoMaD。
4. **模型扩展性好**：CDiT在1B参数下比同等参数DiT快4倍、效果好。
5. **无标签数据提升泛化**：加入Ego4D训练后，在未知环境GO Stanford上的LPIPS从0.658降至0.652，DreamSim从0.478降至0.464，表明视觉先验有益。

### 优点
- **高效架构CDiT**：线性复杂度于帧数，易于扩展到长上下文和更大模型。
- **灵活规划**：可融入任意硬约束（如禁止某方向移动），无需重新训练。
- **多源数据融合**：同时使用机器人和人类视频，并利用无标签数据提升泛化。
- **排名能力**：可即插即用地改进已有导航策略（如NoMaD）。
- **简单实现**：基于VAE和扩散模型，不依赖3D先验或复杂SLAM。

### 不足与局限
1. **模式坍塌问题**：在分布外（未知环境）数据上，模型逐渐失去上下文，生成类似训练数据的结果（图10）。
2. **动态物体建模弱**：难以准确模拟行人等动态物体的运动，影响了社交场景的规划。
3. **动作空间有限**：当前仅使用3自由度动作（平移+偏航），未扩展到6自由度或机器人操作。
4. **泛化验证有限**：仅在一个未知数据集（GO Stanford）上定量评估，且预测时间短（4秒），长期规划效果未知。
5. **计算成本高**：虽然CDiT更高效，但1B参数模型仍需64张H100训练，实际部署可能仍有障碍。

（完）
