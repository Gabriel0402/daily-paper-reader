---
title: Subobject-level Image Tokenization
title_zh: 子对象级图像分词化
authors: "Delong Chen, Samuel Cahyawijaya, Jianfeng Liu, Baoyuan Wang, Pascale Fung"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=imkFoKwFwd"
tags: ["query:mmseg"]
score: 7.0
evidence: SAM模型用于子对象级分词化
tldr: 论文探索了包括SAM在内的多种子对象级图像分词方法，提出EPOC分词器结合边界检测和分水岭分割，无需像素遗漏。在五个数据集上评估表明，EPOC的分割与人类标注的视觉形态高度一致，产生更单义的token并显著提升效率，为图像理解提供新的表示基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 809, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 809, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1742, \"height\": 769, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1730, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1708, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1764, \"height\": 1235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1763, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1749, \"height\": 1512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1729, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1750, \"height\": 794, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 310, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-imkfokwfwd/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1733, \"height\": 901, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-imkfokwfwd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 834, \"height\": 590, \"label\": \"Table\"}]"
motivation: 基于patch的图像分词忽略了视觉世界的形态，限制了图像理解的效果和效率。
method: 提出子对象级自适应token分割，包括超像素、SAM和高效的EPOC分词器，EPOC结合边界检测与分水岭分割。
result: EPOC在多个数据集上分割质量接近人工标注，且具有计算效率优势。
conclusion: 子对象级分词能更好捕捉视觉形态，提升下游任务性能。
---

## Abstract
Patch-based image tokenization ignores the morphology of the visual world, limiting effective and efficient learning of image understanding. Inspired by subword tokenization, we introduce subobject-level adaptive token segmentation and explore several approaches, including superpixel, SAM, and a proposed Efficient and PanOptiC (EPOC) image tokenizer. Our EPOC combines boundary detection--a simple task that can be handled well by a compact model--with watershed segmentation, which inherently guarantees no pixels are left unsegmented. Intrinsic evaluations across 5 datasets demonstrate that EPOC's segmentation aligns well with human annotations of both object- and part-level visual morphology, producing more monosemantic tokens and offering substantial efficiency advantages. For extrinsic evaluation, we designed a token embedding that handles arbitrary-shaped tokens, and trained VLMs with different tokenizers on 4 datasets of object recognition and detailed captioning. The results reveal that subobject tokenization enables faster convergence and better generalization while using fewer visual tokens.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：基于固定大小 patch 的图像分词（如 ViT 的 16×16 网格）忽略了视觉世界的形态结构，导致两个矛盾：大 patch 产生多义性（polysemanticity）token，小 patch 则造成 token 冗余和计算浪费。  
- **背景与动机**：受到 NLP 中 subword 分词（如 BPE）成功解决“罕见词”和“形态结构”的启发，论文提出在图像中引入**子对象级（subobject-level）**自适应分词，类比 subword 之于 word。子对象对应物体部件、子部件等语义连贯的单元，符合认知科学中“识别即组件”理论（Recognition-by-Components）。  
- **整体含义**：通过自适应分割出形态学上有意义的 token，可以提升视觉表征的单义性、学习效率和泛化能力，为图像理解提供新的表示基础。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将图像分词分解为**token 分割**（生成 token 索引图 M）和**token 嵌入**（将每个分割区域编码为向量）。目标是设计高效、全面、与语义边界对齐的分割方法，然后设计能处理任意形状 token 的嵌入方式，供视觉-语言模型（VLM）使用。  
- **关键技术细节**：
  - **EPOC（Efficient and PanOptiC）**：
    - 先训练一个极轻量的**边界检测模型**（基于 SegFormer-b0，仅 3.7M 参数），在 SA-1B 数据集上训练，输入图像直接预测像素级边界概率图 P。
    - 然后对 P 应用**分水岭算法（watershed）**：将 P 视为地形表面，低概率区域作为种子（seed），通过阈值 t 控制种子多少，进而控制分割粒度；洪水过程自动生成完整、无遗漏的分割（panoptic）。
    - 计算复杂度 O(1)，与生成 token 数无关；模型小、推理快。
  - **其他方法**：论文还探索了超像素（SLIC）、SAM 及其变体（FastSAM、MobileSAMv2）、对象级全景分割（Mask2Former、OneFormer）等。
  - **token 嵌入**：为处理动态空间布局和非规则形状，将每个 token 的内容（通过平均池化视觉特征图得到）与位置（包围盒 + 裁剪 mask 编码）拼接后经 MLP 融合，作为 VLM 的输入 token。

## 3. 实验设计：数据集 / 场景、benchmark、对比方法

- **内在评估（intrinsic）**：
  - 数据集（5 个）：COCO（COCONut 标注）、ADE-20K（物体级标注）；PPP（Pascal Panoptic Parts）、PartImageNet++（PIN++）、SA-1B（子对象级标注）。
  - 评估指标：边界精度-召回（对齐形态）、token 单义性分数（不跨越语义边界）、计算效率（FPS、GPU 利用率）。
  - 对比方法：patch 分词（不同 patch 大小）、对象级（Mask2Former、OneFormer）、子对象级（SLIC、SAM ViT-B/H、FastSAM、MobileSAMv2、EPOC）。

- **外在评估（extrinsic）**：
  - 数据集（4 个）：ImageNet-1K（物体分类）、ShareGPT4V（详细描述）、Pixmo-cap（密集描述）、CLEVR-cap（新构建的合成场景描述，涉及计数、空间推理）。
  - 基准：patch 分词基线，对比对象级（Mask2Former）和子对象级（SLIC、EPOC）。
  - 消融实验：不同视觉嵌入（DINOv2、CLIP、SD3 VAE、原始 RGB 像素）、不同 LLM 大小（1.7B vs 350M）、不同分割阈值 t、token 截断鲁棒性等。

## 4. 资源与算力

- **边界检测模型训练**：单机 8×A100，batch size 64，学习率 1e-4，AdamW，在 SA-1B 上训练 2 个 epoch，5000 warmup steps。图像缩放到 1024×1024。
- **推理效率测试**：NVIDIA V100（32GB） + 30 CPU cores，逐步增加并行进程，记录 FPS 和 GPU 利用率。
- **外征 VLM 训练**：使用 Llama 架构的 LLM（最大 1.7B 参数），训练分别在 CLEVR-cap（30 epoch）、ImageNet-1K（1 epoch）、ShareGPT4V（1 epoch）、Pixmo-cap（3 epoch），batch size 512/256，AdamW，学习率 1e-4，混合精度 bf16。论文未报告总 GPU 小时数，但规模可控。

## 5. 实验数量与充分性

- **实验数量**：内在评估 5 个数据集 × 多种方法（约 15 种配置），外在评估 4 个数据集 × 多种 tokenizer + 多种嵌入 + 多种 LLM 大小 + 截断实验，加上消融（不同视觉编码器、不同池化、不同阈值等），总计约 20–30 组独立实验。
- **充分性与公平性**：
  - 内在评估涵盖边界对齐、单义性、效率三个维度，较全面。
  - 外在评估中控制 token 数近似、训练配置一致，确保公平对比。
  - 消融实验覆盖了关键变量（嵌入类型、模型大小、粒度控制），有力地支撑了结论。  
  - 但未在更大规模 VLM（如 7B+）或更多下游任务（如检测、分割）上验证，覆盖范围有限。

## 6. 论文的主要结论与发现

- **子对象级分词显著优于 patch 和对象级**：在所有外在评估数据集上，EPOC 和 SLIC 在使用更少 token 的情况下，达到更低的有效困惑度（valid perplexity），收敛更快，泛化更好。
- **EPOC 的内在性能接近 SAM，但效率高出数个量级**：仅 3.7M 参数，最大 FPS 17.1（SAM ViT-B 仅 0.6 FPS），GPU 利用率<10%，且分割完整性更好（无遗漏区域）。
- **token 单义性优势**：子对象级方法能达到 >90% 的单义性分数，而对象级方法受限于词汇表外物体，大多<60%。
- **鲁棒性**：EPOC 对 token 截断（丢弃小 token）表现鲁棒，进一步提升效率的可能性。
- **结论**：自适应、形态感知的分词是提升视觉模型效率与效果的有效方向。

## 7. 优点

- **方法创新**：首次系统性地将“子对象级”概念引入图像分词，并设计 EPOC 巧妙结合边界检测（简单任务，轻量模型即可）和分水岭算法（自然保证全面覆盖），实现高质高效。
- **模型极简高效**：边界检测仅 3.7M 参数，推理复杂度 O(1)；分水岭为非参数算法，可在 CPU 上快速运行。
- **评估全面**：同时进行内在（对齐、单义性、效率）和外在（下游 VLM 任务）评估，并包含多种消融，论证充分。
- **实用性强**：EPOC 的吞吐量足以配合 VLM 训练流水线，且不占用 GPU 显存，易于集成。

## 8. 不足与局限

- **边界预测精度限制**：SegFormer-b0 输出特征图仅为输入分辨率的 1/4，导致非常细小的结构（如发丝、小字体）可能被忽略。
- **LLM 规模有限**：外在实验仅使用 1.7B LLM，未在更大模型（如 7B/13B）上验证，结论的泛化性存疑。
- **额外预处理开销**：即使 EPOC 很快，仍需额外的分割步骤，在延迟敏感场景可能不占优；但论文指出在视频等 token 数爆炸的场景下，token 减少的收益可能更大。
- **丢弃 intra-token 空间结构**：每个 token 内像素被池化，丢失内部细节，可能对需要像素级精确度的任务（如图像编辑）不利。
- **未探索端到端联合学习**：分割模型是独立预训练的，未与下游 VLM 联合优化，可能限制适配性。
- **覆盖任务有限**：外征评估仅含分类和描述，未涉及检测、分割、视觉问答等，有待进一步验证。

（完）
