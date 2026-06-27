---
title: Neuro-Symbolic Evaluation of Text-to-Video Models using Formal Verification
title_zh: 基于形式化验证的文本到视频模型神经符号评估
authors: "Sharan, S P, Choi, Minkyu, Shah, Sahil, Goel, Harsh, Omama, Mohammad, Chinchali, Sandeep"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Sharan_Neuro-Symbolic_Evaluation_of_Text-to-Video_Models_using_Formal_Verification_CVPR_2025_paper.pdf"
tags: ["query:vlm-rl"]
score: 5.0
evidence: 使用类似于时态逻辑的形式化验证技术
tldr: 现有视频生成评估忽略时间保真度。本文提出NeuS-V，利用神经符号形式化验证技术将提示转换为时序规范，严格评估文本-视频对齐精度，为安全关键应用提供可靠度量。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1808, \"height\": 944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 827, \"height\": 822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 868, \"height\": 513, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 734, \"height\": 1265, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1531, \"height\": 411, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 824, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-sharan-neuro-symbolic-evaluation-of-text-to-video-models-using-formal-verification-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 137, \"label\": \"Table\"}]"
motivation: 现有视频评估指标忽视时间对齐，不适用于安全关键应用。
method: 将提示转换为形式化规范，使用神经符号方法验证文本与视频的时间对齐。
result: 在多个视频生成模型上验证了该指标与人类判断的一致性。
conclusion: NeuS-V为评估视频时间保真度提供了形式化工具。
---

## Abstract
Recent advancements in text-to-video models such as Sora, Gen-3, MovieGen, and CogVideoX are pushing the boundaries of synthetic video generation, with adoption seen in fields like robotics, autonomous driving, and entertainment. As these models become prevalent, various metrics and benchmarks have emerged to evaluate the quality of the generated videos. However, these metrics emphasize visual quality and smoothness, neglecting temporal fidelity and text-to-video alignment, which are crucial for safety-critical applications. To address this gap, we introduce NeuS-V, a novel synthetic video evaluation metric that rigorously assesses text-to-video alignment using neuro-symbolic formal verification techniques. Our approach first converts the prompt into a formally defined Temporal Logic (TL) specification and translates the generated video into an automaton representation. Then, it evaluates the text-to-video alignment by formally checking the video automaton against the TL specification. Furthermore, we present a dataset of temporally extended prompts to evaluate state-of-the-art video generation models against our benchmark. We find that NeuS-V demonstrates a higher correlation by over 5x with human evaluations when compared to existing metrics. Our evaluation further reveals that current video generation models perform poorly on these temporally complex prompts, highlighting the need for future work in improving text-to-video generation capabilities. We open-source our benchmark, code, and dataset at https://utaustin-swarmlab.github.io/neusv.

---

## 论文详细总结（自动生成）

# 基于形式化验证的文本到视频模型神经符号评估——详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有文本到视频（T2V）模型的评估指标过度聚焦于视觉质量（如清晰度、平滑度），严重忽略了**时间保真度**和**文本-视频对齐**。这在安全关键场景（如自动驾驶、机器人、教育）中可能产生误导。
- **背景**：当前主流基准（如VBench）虽然评估多个维度，但缺乏对事件时序、因果关系的严格检验，且“神经网络评估神经网络”的方式缺乏可解释性与鲁棒性。
- **目标**：提出一种可解释、形式化的评估方法，能准确衡量生成视频是否按提示要求的顺序发生事件。

## 2. 方法论
### 核心思想
融合神经网络与符号形式化验证：将自然语言提示转换为**时态逻辑（TL）规范**，将视频转换为**自动机（Automaton）**，然后通过**概率模型检查**计算满足概率，以此作为对齐分数。

### 关键技术细节（5步流程）
1. **PULS提示理解**：
   - 两个模块：Text-to-Proposition（T2P）提取原子命题 `P`；Text-to-TL（T2TL）生成TL规范 `Φ`。
   - 使用LLM（GPT-4o/o1-preview）+ 优化后的少样本示例集（通过MIPROv2+DSPy优化）。
   - 支持四种评估模式：对象存在、空间关系、对象-动作对齐、整体一致性。

2. **语义置信度提取**：
   - 使用VLM（InternVL2-8B）对每一帧（或三帧窗口）计算每个命题 `p_i` 为真的置信度 `c_i`，通过softmax归一化。
   - 校准：通过假阳性阈值 `γ_fp` 映射得到校准置信度 `c*_i`。

3. **视频自动机构建**：
   - 将视频表示为离散时间马尔可夫链（DTMC）：状态对应命题的真值组合，转移概率由置信度乘积决定。
   - 构建函数 `ξ`：`A_V = ξ(P, C*)`。

4. **形式化验证**：
   - 使用STORM概率模型检查器，计算满足概率 `P[A_V |= Φ]`。

5. **分数校准**：
   - 将满足概率通过经验累积分布函数（ECDF）映射到最终NeuS-V分数（各模式平均）。

### 算法伪代码
- 滑动窗口（步长=帧窗口大小w），对每个窗口提取置信度，累积后构造自动机，验证，得到分数。

## 3. 实验设计
### 数据集/场景
- **自建Prompt套件**：360个提示，覆盖4个主题（自然、人类/动物活动、对象交互、驾驶数据），3个复杂度等级（基础/中级/高级，基于时态运算符数量）。
- **人类标注子集**：160个提示，请标注者分离视觉质量与文本-视频对齐。
- **MSR-VTT**：真实视频字幕数据集，构建正（匹配）负（不匹配）样本对测试区分能力。

### Benchmark与对比方法
- **对比指标**：VBench（视觉质量导向）及基于纯VLM的方法（GPT-4o+LLaMa-3.2-11B、GPT-4o+LLaVA-Video-7B）。
- **评估的T2V模型**：Gen-3, Pika（商用闭源），T2V-Turbo-v2, CogVideoX-5B（开源）。
- **评价标准**：Pearson相关系数（与人类标注的对齐分数）、得分均值与标准差。

### 消融实验
- 上下文帧数（1帧 vs 3帧）
- VLM选择（InternVL2-8B vs LLaMa3.2-11B）
- 去除形式化语言（替换为纯VLM问答）

## 4. 资源与算力
- **生成模型运行环境**：8×A100 GPU（默认超参数）。未明确说明NeuS-V自身训练资源（其VLM为预训练，PULS依赖API，模型检查STORM为CPU计算）。因此算力需求主要来自T2V模型推理，而非NeuS-V本身。

## 5. 实验数量与充分性
- **主要实验**：表1展示4个模型在360个prompt上的得分及与160个人类子集的相关系数；图4展示各模型NeuS-V vs VBench的散点图及相关系数。
- **消融实验**：图6（形式语言重要性）、表3（视觉上下文）、表4（VLM选择），共计3组独立消融。
- **鲁棒性验证**：表2在MSR-VTT上正负样本区分（NeuS-V差值0.52优于VBench的0.38）。
- **充分性评价**：实验覆盖了多种模型、多种复杂度、多种评估模式，并做了必要的消融，设计客观（使用相同的人类标注子集对比）。但未在更大规模真实视频数据集（如VidOR）上测试，场景覆盖可进一步扩展。

## 6. 主要结论与发现
- **NeuS-V与人类对齐相关性显著优于VBench**：在图4中，NeuS-V的Pearson系数在0.48~0.62之间，而VBench为0.01~0.15；NeuS-V相关性高出5倍以上。
- **当前T2V模型在时态复杂提示上表现差**：表1显示，高级复杂度（含3个时态运算符）得分明显低于基础级（如Gen-3从0.774降至0.692）。
- **形式语言不可或缺**：图6中，纯VLM（GPT-4o+LLaMa/LLaVA）的相关系数仅为0.10~0.30，远低于NeuS-V。
- **三帧上下文比单帧更好**（表3），InternVL2-8B优于LLaMa3.2（表4）。

## 7. 优点
- **创新性**：首次将形式化验证引入T2V评估，提供了可解释、可数学证明的时序对齐度量。
- **可解释性**：自动机结构和TL规范直观展示视频内容是否符合预期事件流。
- **相关性高**：与人类评估的强相关验证了其有效性。
- **模块化**：PULS可独立用于其他时序任务；VLM可替换升级。

## 8. 不足与局限
- **无法惩罚无关元素**：视频中若出现提示未要求的额外对象或动作，NeuS-V不会因此扣分，可能导致分数虚高。
- **依赖VLM质量**：VLM的置信度校准和语义理解直接影响自动机构建，目前仅测试了两种VLM，泛化性待验证。
- **帧窗口大小影响**：仅实验了1帧和3帧，未探索更大窗口或自适应采样；上下文长度受限。
- **计算开销**：需要对每一帧/窗口调用VLM，对长视频可能较慢；目前未给出实时性估计。
- **数据集规模有限**：自建提示库仅360个，真实视频测试仅用MSR-VTT，可能未覆盖复杂动态场景（如多人交互、长时间跨度的故事）。
- **未探讨如何利用反馈改进生成**：尽管可以作为训练奖励信号，但文中仅作为评估工具，未验证其实用性。

（完）
