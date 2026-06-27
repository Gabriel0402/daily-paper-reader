---
title: Embodied Scene Understanding for Vision Language Models via MetaVQA
title_zh: 通过MetaVQA实现视觉语言模型的具身场景理解
authors: "Wang, Weizhen, Duan, Chenda, Peng, Zhenghao, Liu, Yuxin, Zhou, Bolei"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Wang_Embodied_Scene_Understanding_for_Vision_Language_Models_via_MetaVQA_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 7.0
evidence: 针对自主驾驶等移动应用的VLM具身场景理解基准
tldr: 针对VLM在具身智能应用中缺乏标准化闭环基准的问题，本文提出MetaVQA基准，利用Set-of-Mark提示和俯视图标注自动生成真实交通场景的问答对，通过VQA和闭环仿真评估VLM的空间推理和顺序决策能力，为自主驾驶等移动应用提供标准评估平台。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1785, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1021, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1804, \"height\": 805, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1802, \"height\": 658, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 401, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 397, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 801, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-wang-embodied-scene-understanding-for-vision-language-models-via-metavqa-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 449, \"label\": \"Table\"}]"
motivation: 缺乏标准化的闭环基准来评估VLM在空间推理和顺序决策方面的能力。
method: 提出MetaVQA基准，利用Set-of-Mark提示和俯视图标注自动生成问答对。
result: 在nuScenes和Waymo数据集上生成多样化的交通场景问答对。
conclusion: 为评估和提升VLM的具身智能提供标准基准。
---

## Abstract
Vision Language Models (VLMs) demonstrate significant potential as embodied AI agents for various mobility applications. However, a standardized, closed-loop benchmark for evaluating their spatial reasoning and sequential decision-making capabilities is lacking. To address this, we present MetaVQA: a comprehensive benchmark designed to assess and enhance VLMs' understanding of spatial relationships and scene dynamics through Visual Question Answering (VQA) and closed-loop simulations. MetaVQA leverages Set-of-Mark prompting and top-down view ground-truth annotations from nuScenes and Waymo datasets to automatically generate extensive question-answer pairs based on diverse real-world traffic scenarios, ensuring object-centric and context-rich instructions. Our experiments show that fine-tuning VLMs with the MetaVQA Dataset significantly improves their embodied scene understanding, which is evident not only in improved VQA accuracy but also in emerging safety-aware driving maneuvers. In addition, the learning exhibits strong transferability from simulation to real-world observation. The project webpage is at https://metadriverse.github.io/metavqa.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉语言模型（VLM）在机器人控制、自主驾驶等具身智能应用中展现出潜力，但缺乏一个标准化、闭环的基准来评估其空间推理和顺序决策能力。现有工作（如DriveLM、ELM、DriveVLM）的评价方式各异，存在以下问题：
  - 不同数据集使用异构的文本和视觉表达（如用像素坐标、相机ID等引用物体），不通用、不直观，难以进行零样本评估和比较。
  - 现有评估多为开环VQA任务，缺乏与环境的交互；而闭环评估需要手动或依赖世界模型，成本高且易退化。
  - 真实数据集难以覆盖安全关键的边缘场景。
- **整体含义**：本文提出 MetaVQA 基准，旨在为通用VLM提供一个标准化、可扩展的具身场景理解评估与微调平台，涵盖开环VQA和闭环仿真两种任务，并利用大规模真实交通场景和合成数据提升VLM的自主驾驶能力。

## 2. 方法论

### 核心思想
- 利用 **Set-of-Mark（SoM）提示** 对图像中的物体进行清晰、无歧义的标注（用数字标签+边界框），使VLM可以直观地关联文本引用与视觉区域。
- 基于真实交通场景（nuScenes、Waymo Open Motion Dataset）的场景图，通过程序化查询自动生成大量多选VQA对，覆盖空间关系、具身理解、物体定位三大类问题。
- 结合 **MetaDrive** 仿真器重建真实场景，实现可控的闭环驾驶评估，包括安全关键场景（通过CAT生成对抗性车辆）。

### 关键技术细节
1. **场景聚合**：
   - 从nuScenes提取3D场景图（每个节点包含物体空间/姿态信息，边表示空间关系）。
   - 利用ScenarioNet将Waymo数据转换为统一格式，在MetaDrive中重建，渲染出第一人称RGB图像。
2. **Set-of-Mark标注**：
   - 对真实图像：将3D边界框投影到2D，生成边界框+数字标签。
   - 对仿真图像：利用实例分割相机直接提取2D边界框。
   - 认为感知任务基本可解决，直接标注物体不是泄露信息，而是提供清晰的通信渠道。
3. **问答生成**：
   - 30种问题类型，分为三大超类：空间问题（距离、相对方位、速度等）、具身问题（碰撞预测、行为后果）、定位问题（识别标记区域对应的数字标签）。
   - 采用多选格式，答案离散化为自然语言短语（如“很近0-2m”“前侧”等），并包含“解释”字段辅助训练。
   - 生成流程：随机选物体节点 → 基于场景图查询得到正确答案+干扰项 → 生成问题文本和答案。
4. **闭环驾驶任务**：
   - 每5仿真步（0.5秒）接收标注图像+导航指令（目标方向），VLM输出动作（如直行、左转、右转、刹车），映射到固定加速度和转向值。
   - 失败条件：车辆驶出道路。

## 3. 实验设计

### 数据集与场景
- **训练集**：150,000个VQA问题（来自400个nuScenes场景和6,900个Waymo场景），其中50,000来自仿真Waymo、50,000来自真实nuScenes、50,000来自仿真nuScenes。
- **测试集**：9,725个问题（212个交通场景），约半数为仿真观察、半数为真实图像。
- **闭环评估**：120个驾驶场景（60个nuScenes真实场景 + 60个CAT生成的安全关键场景）。
- 总时长：59,682秒（16.5小时）驾驶记录，4,305,450个候选问题。

### 基准与对比方法
- **VQA基准**：对比随机基线（随机猜测）、LLaVA-NeXT（7B）、LLaVA-OneVision、GPT-4o、Qwen2、Llama3.2、InternVL2-8B等VLM，并展示Qwen2、Llama3.2、InternVL2-8B的微调版本。
- **闭环基准**：对比随机策略、刹车策略、直行策略，以及上述VLM的零样本和微调版本（包括InternVL2-4B）。
- 评价指标：VQA准确率（总体/仿真部分/真实部分）、解析失败率；闭环指标包括碰撞率、离路率、平均位移误差（ADE）、最终位移误差（FDE）、路径完成率。

### 消融与附加实验
- **Sim-to-Real迁移**：对比仅仿真训练、仅真实训练、两者结合训练的InternVL2-8B在真实测试集上的准确率。
- **数据规模缩放**：分别使用9,375、37,500、150,000个问题微调InternVL2-8B，观察性能变化。
- **人机评估**：6位参与者回答35个抽样问题，平均准确率88%。

## 4. 资源与算力

- **论文未明确说明** 使用的GPU型号、数量、训练时长等具体算力信息。仅提及使用了MetaVQA数据集进行微调，但未提供训练计算资源细节。

## 5. 实验数量与充分性

- **实验组数**：
  - VQA：基准零样本测试（8个模型）+ 微调测试（3个模型 × 3个训练集变体）共约17组。
  - 闭环：6个模型（包括随机/策略基线）各进行一次评估，共约12组数据（含预处理版本）。
  - 消融：Sim-to-Real迁移（4组）、数据规模（3组）、人机评估（1组）。
  - 合计约20余组实验。
- **充分性与公平性**：
  - 实验覆盖了多种代表性VLM（不同规模、架构），包括开源和闭源模型。
  - 使用统一的测试集和指标，对比模型在相同条件下的表现。
  - 闭环任务使用了未见过的场景（训练数据中不含相同格式的驾驶提示），验证了泛化性。
  - 消融实验证明了Sim-to-Real迁移的有效性和数据规模的重要性。
  - 局限性：VLM在闭环任务中可能出现碰撞率异常（如InternVL2-8B微调后碰撞率升高），作者认为与预训练差异有关，但未深入解释。

## 6. 主要结论与发现

1. **MetaVQA 可有效评估和提升VLM的具身场景理解**：微调后 VLM 在 VQA 任务上准确率显著提升（如 InternVL2-8B 从 59.2% 升至 86.9%），且在闭环驾驶任务中表现出更好的路线完成率和更低的事故率。
2. **Sim-to-Real 迁移有效**：仅使用仿真数据微调即可在真实图像测试集上获得显著提升（从 63.2% 到 85.8%），说明仿真场景有助于学习通用场景理解。
3. **数据规模正相关**：训练数据越多，VLM性能越好。
4. **Set-of-Mark 提示是有效的通信方式**：多数VLM在定位任务中准确率高（平均69.6%），支持使用数字标签引用物体。
5. **闭环驾驶能力提升**：微调后VLM能够更安全地应对障碍物（如转向避开危险或减速），证明了学习到的具身知识可迁移到新任务。

## 7. 优点

- **标准化评估**：统一的多选格式、Set-of-Mark标注、清晰的问题分类，使得不同VLM之间的比较公平且可重复。
- **大规模高质量数据**：自动生成430万+个问题，覆盖丰富的真实场景（nuScenes+Waymo）和仿真场景，包含安全关键场景。
- **开环+闭环双维度评估**：不仅评测静态理解，还通过仿真实现交互测试，更贴近实际应用。
- **Sim-to-Real 迁移验证**：证明了合成数据在实际应用中的价值，减少了真实数据收集成本。
- **良好的人机一致性**：人类评估准确率88%，说明问题设计直观易懂。

## 8. 不足与局限

- **观察模态单一**：仅使用单视角RGB图像，缺乏多相机融合或历史帧信息，可能限制复杂场景下的决策能力。
- **感知假设**：假设物体检测已解决，要求输入图像已标注边界框和数字标签，实际部署中需要额外感知模块。
- **动作空间简化**：闭环任务中动作映射为固定加速度和转向，与真实车辆动力学有差距。
- **碰撞率不一致**：部分微调模型在闭环中碰撞率反而升高（如InternVL2-8B从0.325升至0.367），作者未给出充分解释。
- **算力信息缺失**：未报告训练所需的计算资源，影响可复现性。
- **问题覆盖局限**：虽然30种问题类型较丰富，但未涵盖所有具身理解维度（如长期规划、多智能体交互）。
- **仅聚焦自主驾驶场景**：方法通用性需在其他具身任务（如机器人操控）中验证。

（完）
