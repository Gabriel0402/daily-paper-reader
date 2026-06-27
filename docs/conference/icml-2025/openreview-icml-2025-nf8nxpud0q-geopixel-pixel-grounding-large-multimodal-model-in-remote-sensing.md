---
title: "GeoPixel: Pixel Grounding Large Multimodal Model in Remote Sensing"
title_zh: GeoPixel：遥感大模型的像素级定位
authors: "Akashah Shabbir, Mohammed Zumri, Mohammed Bennamoun, Fahad Shahbaz Khan, Salman Khan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=nF8NxPUd0q"
tags: ["query:mmseg"]
score: 9.0
evidence: 遥感领域像素级定位的大多模态模型
tldr: 大多模态模型在遥感领域表现不佳，因视角、尺度差异及缺乏细粒度数据。本文提出GeoPixel，首个端到端高分辨率遥感大模型，支持像素级定位。通过收集像素级RS对话数据并设计专用架构，在遥感视觉对话和定位任务上显著优于通用模型。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1734, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 800, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1694, \"height\": 1002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 422, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 466, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1777, \"height\": 1019, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nf8nxpud0q/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 444, \"height\": 226, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1780, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nf8nxpud0q/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 859, \"height\": 232, \"label\": \"Table\"}]"
motivation: 通用大模型在遥感场景下细粒度理解能力不足，且缺乏像素级标注数据。
method: 构建像素级遥感对话数据集，设计端到端高分辨率架构实现像素级定位。
result: 在遥感视觉对话和定位基准上，GeoPixel超越现有通用模型。
conclusion: 像素级定位能力可极大提升遥感大模型的细粒度理解。
---

## Abstract
Recent advances in large multimodal models (LMMs) have recognized fine-grained grounding as an imperative factor of visual understanding and dialogue. However, the benefits of such representation in LMMs are limited to the natural image domain, and these models perform poorly for remote sensing (RS). The distinct overhead viewpoint, scale variation, and presence of small objects in high-resolution RS imagery present a unique challenge in region-level comprehension. Moreover, the development of the grounding conversation capability of LMMs within RS is hindered by the lack of granular, RS domain-specific grounded data. Addressing these limitations, we propose GeoPixel - the first end-to-end high-resolution RS-LMM that supports pixel-level grounding. This capability allows fine-grained visual perception by generating interleaved masks in conversation. GeoPixel supports up to 4K HD resolution in any aspect ratio, ideal for high-precision RS image analysis. To support the grounded conversation generation (GCG) in RS imagery, we curate a visually grounded dataset GeoPixelD through a semi-automated pipeline that utilizes set-of-marks prompting and spatial priors tailored for RS data to methodically control the data generation process. GeoPixel demonstrates superior performance in pixel-level comprehension, surpassing existing LMMs in both single-target and multi-target segmentation tasks. Our methodological ablation studies validate the effectiveness of each component in the overall architecture. Our code and data will be publicly released.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：大型多模态模型（LMM）在自然图像领域的细粒度定位（grounding）已取得显著进展，但应用于遥感（RS）影像时性能大幅下降。
- **核心问题**：遥感图像具有独特的俯视视角、极大的尺度变化、大量小目标等特点，现有LMM通常仅支持低分辨率输入且仅能输出边界框级别的粗粒度定位，缺乏像素级理解能力。同时，遥感领域缺乏细粒度的、带像素级标注的对话数据。
- **整体目标**：本文提出**GeoPixel**——首个端到端的高分辨率遥感大模型，支持**像素级定位**（pixel grounding），能够在对话中生成交错的物体分割掩码，实现精细的视觉感知。

## 2. 论文提出的方法论

- **核心思想**：结合高分辨率自适应图像切分、大语言模型、预训练的视觉编码器和分割解码器，实现像素级的接地对话生成（GCG）。
- **关键技术细节**：
  - **自适应图像切分**：采用动态网格划分，将输入图像缩放并填充至接近的网格尺寸（`gh × gw`），划分为`k1×k2`个非重叠补丁（`p`个），同时生成一个全局视图（560×560）。特征嵌入通过可学习标记和分隔符连接后输入LLM。支持最高4K分辨率，适应任意宽高比。
  - **视觉编码器**：使用缩放的CLIP ViT-L/14，基础分辨率B=560。
  - **大语言模型**：采用InternLM2 7B，通过两层MLP视觉投影器将图像特征映射到语言空间。使用**Partial LoRA**（仅应用于视觉 token）实现高效跨模态对齐。
  - **像素定位**：在词表中加入`<SEG>` token，其最后一层嵌入通过文本投影层（两层MLP）映射到像素解码器。接地视觉编码器使用预训练的SAM-2编码器（冻结），像素解码器（轻量）处理视觉特征和LLM嵌入，生成分割掩码。
  - **数据集GeoPixelD**：通过半自动流水线构建，包含53,816个接地短语、600,817个物体掩码。流水线包括：
    - 整体场景标注（holistic image annotation）：使用IXC模型生成简洁场景描述。
    - 个体实例标注（individual instance annotation）：利用**SOM（Set-of-Mark）提示**结合类别和位置先验，逐对象生成属性描述。
    - 集群/密集目标标注（cluster/crowd annotation）：对剩余小/密集物体通过3×3、2×2、1×2等网格进行分组描述。
    - 统一标注与语言标记：将三类标注用Llama-3.1-8B合并，保留标有`短语-编号`的关键词以关联掩码。
- **算法流程**（文字描述）：
  1. 输入高分辨率遥感图像，自适应切分为局部补丁和缩放全局视图。
  2. 通过CLIP编码器提取特征，经投影器送入LLM，并与用户文本交互。
  3. LLM生成含`<SEG>` token的响应文本，对应 token嵌入经文本投影层传入像素解码器。
  4. 解码器结合SAM-2编码器输出的多尺度视觉特征，生成多个分割掩码。

## 3. 实验设计

- **使用的数据集**：
  - **GeoPixelD**（训练集）：基于iSAID训练集图像，通过自身流水线生成GCG描述（53,816短语，600,817掩码）。
  - **RS-GCG基准**（测试集）：基于iSAID验证集图像，人工精细标注5,427个描述、61,384个对象。
  - **RRSIS-D**（遥感引用分割数据集）：用于评估引用分割能力。
  - **VRSBench**（基于DOTA v2和DIOR）：用于评估引用检测（RED）任务。
- **评估任务与指标**：
  - **RS-GCG**（接地对话生成）：CIDEr、METEOR、CLAIR（GPT-4o评估）、AP50、mIoU、Recall（分单目标、多目标、总体）。
  - **RRSIS**（引用分割）：P@0.5、oIoU、mIoU。
  - **RED**（引用检测）：Acc@0.5 / Acc@0.7（分唯一对象、非唯一对象、总体），支持水平/定向边界框。
- **对比方法**：
  - RS-GCG：**LISA†**（微调）、**PixelLM†**（微调）、**GLaMM**（零样本 & 微调GLaMM-FT）。
  - RRSIS：RRN、CSMA、LSCM、CMPC、BRINet、LGCE、LAVT、RMSIN 等。
  - RED：MiniGPT-v2、LLaVA-1.5、Mini-Gemini、GeoChat、GeoPix。
- **实验设置**：所有微调基线均使用GeoPixelD训练数据重新训练/微调。

## 4. 资源与算力

- **训练设备**：2张 NVIDIA A6000-48GB GPU。
- **训练时长**：约3天（10个epoch，有效batch size=20，最大学习率3e-4，余弦衰减）。
- **模型规模**：7B参数（InternLM2-7B LLM + CLIP ViT-L + SAM-2编码器）。
- **备注**：论文明确给出了GPU型号、数量和训练时间。

## 5. 实验数量与充分性

- **实验组数**：
  - 主任务RS-GCG（表2）对比4个基线，报告7项指标。
  - RRSIS任务（表3）对比10个现有方法，报告P@0.5/oIoU/mIoU。
  - RED任务（表4-5）对比5个基线，报告不同IoU阈值下的Acc。
  - 消融实验：
    - 推理分辨率影响（表6）：3种分辨率（P=1,4,9）。
    - 注释复杂度（表7）：仅实例、仅语义、混合数据，分析mIoU/Recall。
    - 数据复杂度与视觉投影训练（表8）：两组数据子集（Set-1A vs Set-1B）和视觉投影层固定/训练对比。
  - 定性示例（图4-6）及失败案例分析。
- **充分性与公平性**：
  - 所有基线均在同等条件下微调或零样本评估，使用了同一训练数据（GeoPixelD）。
  - 消融实验覆盖了分辨率、注释类型、投影层等关键设计，验证了各组件有效性。
  - 自我批评：论文承认实验存在局限性（如某些场景下掩码关联错误、实例混淆），并讨论了失败案例。
- **总体评价**：实验数量充足，对比全面，消融合理，结果可信。

## 6. 论文的主要结论与发现

- GeoPixel在所有评估任务上显著优于现有LMM基线：
  - RS-GCG：总体AP50达19.0（次优GLaMM-FT仅12.5），mIoU达52.3（次优46.4），Recall 38.8（次优32.8）。
  - RRSIS：P@0.5达80.00（验证集）和83.33（测试集），oIoU达81.77和84.90，超越所有现有专门模型。
  - RED（定向框）：总体Acc@0.5为58.00，远优于GeoChat（24.3）。
- 高分辨率推理（P=9）显著提升CIDEr、mIoU等指标，验证了自适应切分的有效性。
- 混合注释（实例+语义）在复杂场景中更合理，但模型泛化掩码类型仍有挑战。
- 视觉投影层可训练带来性能提升。

## 7. 优点

- **方法创新**：首个支持像素级定位的端到端遥感LMM，结合自适应高分辨率切分与SAM-2解码，实现精细化分割。
- **数据集贡献**：构建了大规模、半自动生成的像素级接地对话数据集GeoPixelD，包含多层级注释，并公开代码与数据。
- **实验全面**：涵盖三项主流任务（对话生成、引用分割、引用检测），对比多个通用/专用模型，消融充分。
- **性能突出**：在两个基准（RS-GCG、RRSIS-D）上取得领先，尤其在多目标分割和引用检测上表现优异。
- **鲁棒设计**：Partial LoRA仅调节视觉token，保留LLM语言能力；SAM-2编码器冻结，保证泛化性。

## 8. 不足与局限

- **掩码歧义问题**：在密集场景中，模型难以正确区分实例掩码与语义掩码，导致重复描述或掩码重叠/碎片化（见图6）。
- **数据集覆盖**：仅基于iSAID数据集（单域），未验证在更多样化遥感数据上的泛化能力。
- **计算成本**：高分辨率推理（P=9）需要更多计算资源，可能限制实时应用。
- **仅支持单一模态**：未融合合成孔径雷达（SAR）、红外等多源数据，未来可扩展。
- **隐私与伦理**：虽然使用公开数据，但高分辨率影像可能涉及隐私，文中提出了相应关注。
- **评价指标局限**：CLAIR指标（LLM评估）可能受GPT-4o偏差影响；召回和IoU在语义掩码场景下解释性有限。

（完）
