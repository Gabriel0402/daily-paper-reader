---
title: "EdgeTAM: On-Device Track Anything Model"
title_zh: EdgeTAM：设备端跟踪一切模型
authors: "Zhou, Chong, Zhu, Chenchen, Xiong, Yunyang, Suri, Saksham, Xiao, Fanyi, Wu, Lemeng, Krishnamoorthi, Raghuraman, Dai, Bo, Loy, Chen Change, Chandra, Vikas, Soran, Bilge"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhou_EdgeTAM_On-Device_Track_Anything_Model_CVPR_2025_paper.pdf"
tags: ["query:mmseg"]
score: 7.0
evidence: 高效的设备端SAM模型用于跟踪和分割
tldr: SAM 2虽强大但计算开销大，难以在移动设备运行。本文提出EdgeTAM，通过2D空间感知器（2D Spatial Perceiver）降低记忆注意力块的计算成本，在保持性能的同时实现移动端推理。在视频分割任务上，EdgeTAM显著压缩了模型并实现了实时运行，拓展了SAM在边缘设备上的应用。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 879, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1822, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1780, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1813, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1641, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1788, \"height\": 582, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1055, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1394, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 738, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 710, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 614, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhou-edgetam-on-device-track-anything-model-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 533, \"height\": 194, \"label\": \"Table\"}]"
motivation: SAM 2在移动设备上推理延迟高。
method: 提出2D Spatial Perceiver替代记忆注意力块，降低计算量。
result: 在移动设备上实现实时视频分割且性能接近原模型。
conclusion: 高效设计使SAM可在边缘设备部署。
---

## Abstract
On top of Segment Anything Model (SAM), SAM 2 further extends its capability from image to video inputs through a memory bank mechanism and obtains a remarkable performance compared with previous methods, making it a foundation model for video segmentation task. In this paper, we aim at making SAM 2 much more efficient so that it even runs on mobile devices while maintaining a comparable performance. Despite several works optimizing SAM for better efficiency, we find they are not sufficient for SAM 2 because they all focus on compressing the image encoder, while our benchmark shows that the newly introduced memory attention blocks are also the latency bottleneck. Given this observation, we propose EdgeTAM, which leverages a novel 2D Spatial Perceiver to reduce the computational cost. In particular, the proposed 2D Spatial Perceiver encodes the densely stored frame-level memories with a lightweight Transformer that contains a fixed set of learnable queries. Given that video segmentation is a dense prediction task, we find preserving the spatial structure of the memories is essential so that the queries are split into global-level and patch-level groups. We also propose a distillation pipeline that further improves the performance without inference overhead. As a result, EdgeTAM achieves 87.7, 70.0, 72.3, and 71.7 J&F on DAVIS 2017, MOSE, SA-V val, and SA-V test, while running at 16 FPS on iPhone 15 Pro Max. The code and models are available at https://github.com/facebookresearch/EdgeTAM.

---

## 论文详细总结（自动生成）

# EdgeTAM: On-Device Track Anything Model 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

SAM 2 通过记忆银行机制将图像分割扩展至视频，成为视频分割领域的基座模型，但其在移动设备（如 iPhone 15 Pro Max）上推理速度极慢（约 1 FPS）。现有优化工作仅聚焦于压缩图像编码器，而本文的基准测试发现，SAM 2 中新增的**记忆注意力模块**同样是延迟瓶颈——即使将图像编码器替换为紧凑型骨干网络，解码器端（尤其是交叉注意力）的计算仍无法满足实时需求。因此，论文旨在使 SAM 2 在保持性能的同时能在移动设备上高效运行，提出了 **EdgeTAM**。

## 2. 论文提出的方法论

### 核心思想
- **2D Spatial Perceiver**：利用可学习查询将密集型帧级记忆特征压缩为少量 token，同时保留 2D 空间结构，从而大幅降低记忆注意力的计算复杂度（从 O(T·C·H²·W²) 降至 O(T·C·H·W·(N_g+N_l))）。
- **蒸馏流程**：分两阶段对齐教师（SAM 2 Hiera-B+）与学生模型的特征：① 图像预训练阶段对齐图像编码器输出；② 视频训练阶段额外对齐记忆注意力输出，提升性能且不增加推理开销。
- 还采用了**渐进式微调**（从 8 帧→16 帧→32 帧训练样本），以延长时序上下文。

### 关键技术细节
1. **2D Spatial Perceiver**：包含两组可学习查询：
   - **全局查询**（Global Latents）：每个查询对整个记忆特征图做全局注意力，输出帧级摘要。
   - **2D 局部查询**（2D Latents）：每个查询仅关注非重叠的局部窗口（类似窗口分区），输出保留空间结构的 token。
   - 二者拼接后作为压缩后的记忆表示，送入后续记忆注意力模块。
2. **记忆注意力加速**：原本需要处理 H×W 个 token（如 64×64=4096），压缩后仅需 N_g+N_l 个 token（如 512 个），计算量减少约 8 倍。
3. **蒸馏损失**：在图像阶段使用 MSE 损失对齐编码器特征；在视频阶段额外使用 MSE 损失对齐记忆注意力输出。任务损失（dice、focal、IoU、occlusion）保持不变。

## 3. 实验设计

### 使用的数据集
- **训练**：SA-1B（图像）、SA-V、DAVIS、MOSE、YTVOS（视频）。
- **评估**：
  - 视频对象分割（VOS）：DAVIS 2017、MOSE、SA-V val/test、YTVOS 2019。
  - 提示式视频分割（PVS）：9 个零样本数据集（如 DAVIS、MOSE、SA-V 等）。
  - 分割一切（SA）：SA-23（含图像和视频）。

### 基准（Benchmark）
- 对比方法：STCN、SwinB-AOT、XMem、Cutie、DEVA、SAM 2、SAM 2.1 等。
- 指标：J&F（视频）、mIoU（图像）、FPS（速度，聚焦 iPhone 15 Pro Max）。

### 主要结果
- EdgeTAM 在 DAVIS 2017 上达到 87.7 J&F，MOSE 70.0，SA-V val 72.3，SA-V test 71.7。
- 在 iPhone 15 Pro Max 上以 16 FPS 运行，比 SAM 2 快 22 倍，同时性能与 SAM 2 相当或略优。
- 在 PVS 任务上，EdgeTAM 显著优于 SAM+XMem++、SAM+Cutie，且接近 SAM 2。

## 4. 资源与算力

论文未明确说明训练所使用的具体 GPU 型号、数量和训练时长。仅提及：
- 图像预训练阶段：batch size 128，训练 2 epoch。
- 视频训练阶段：batch size 256，训练 130K 次迭代。
- 渐进式微调：16 帧和 32 帧训练样本，迭代次数为原始计划的三分之一。
- 默认使用 RepViT-M1 作为图像编码器，教师模型为 SAM 2 Hiera-B+（公开检查点）。

**未明确之处**：GPU 类型（如 A100/V100）、数量、总训练时间等细节缺失。

## 5. 实验数量与充分性

- **多数实验**：包括 VOS 任务在 5 个数据集上的主结果（表 2）、PVS 零样本评估（图 5）、SA 任务评估（表 1）。
- **消融实验**（表 3 a-d）：
  - 比较不同记忆压缩策略（平均池化 vs 2D Perceiver vs 蒸馏）。
  - 查询分配（全局/2D 数量）。
  - 不同骨干网络（ViT-Tiny, RepViT-M1）和不同记忆注意力块数量。
  - 自注意力在 Perceiver 中的必要性。
- **公平性**：与 SAM 2 使用相同的训练数据（除内部数据集外），速度测试在相同设备上（iPhone 15 Pro Max、A100），对比方法包含近期 SOTA。
- **充分性**：实验覆盖了多种任务场景，消融设计合理，能清晰验证各组件贡献。但缺少在真实移动端功耗、内存占用方面的详细报告。

## 6. 论文的主要结论与发现

1. **瓶颈识别**：SAM 2 在移动设备上的延迟瓶颈不仅在于图像编码器，更在于记忆注意力模块，尤其是交叉注意力。
2. **2D Spatial Perceiver 有效性**：通过保持空间结构压缩记忆，可实现 8 倍加速且性能几乎无损。
3. **蒸馏提升**：从 SAM 2 教师蒸馏特征可额外提升 1.3~3.3 J&F，不增加推理成本。
4. **统一模型可行性**：EdgeTAM 同时支持图像/视频分割与跟踪，在移动设备上达到 16 FPS，为首次实现设备端可实时运行的“跟踪一切”模型。

## 7. 优点

- **问题定位精准**：通过细致基准实验（图 2）揭示以往被忽略的瓶颈（记忆注意力）。
- **方法新颖且高效**：2D Spatial Perceiver 结合全局与局部查询，既压缩信息又保留密集预测所需的空间结构，设计巧妙。
- **实用性强**：可在最新 iPhone 上实时运行，且性能接近服务器级 SAM 2；代码和模型已开源。
- **消融全面**：从压缩策略、查询设计、骨干选择到蒸馏组件均有验证，结论可靠。
- **训练技巧**：渐进式微调利用 EdgeTAM 低显存优势，进一步提升性能。

## 8. 不足与局限

- **实验覆盖局限**：未提供在多种移动设备（如安卓、低端 NPU）上的速度/功耗测试，仅适用于 iPhone 15 Pro Max。
- **训练资源信息缺失**：未报告 GPU 型号、数量、训练总时间，不利于同行复现和效率评估。
- **小物体跟踪粒度问题**：定性结果（图 6）显示，当目标存在局部细节（如鸟脚）时，EdgeTAM 可能丢失细粒度掩码（例如仅跟踪身体而不包含脚），原因可能在于压缩丢失了局部细节。
- **对比方法时效性**：部分对比方法（如 STCN、XMem）为 2021-2022 年版本，缺乏与最近更强基线（如 SAM 2.1 更小变体）的直接对比（表 2 中 SAM 2.1-B+ 仍优于 EdgeTAM 在部分指标上）。
- **蒸馏依赖强教师**：需要预先训练好的 SAM 2 Hiera-B+ 教师，且教师模型未公开进一步优化的细节。

（完）
