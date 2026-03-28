<div align="center">

> 📌 本文档汉化自 [microsoft/VibeVoice](https://github.com/microsoft/VibeVoice)

## 🎙️ VibeVoice：开源前沿语音 AI
[![项目主页](https://img.shields.io/badge/项目-主页-blue?logo=githubpages)](https://microsoft.github.io/VibeVoice)
[![Hugging Face](https://img.shields.io/badge/HuggingFace-合集-orange?logo=huggingface)](https://huggingface.co/collections/microsoft/vibevoice-68a2ef24a875c44be47b034f)
[![TTS 报告](https://img.shields.io/badge/TTS-报告-red?logo=arxiv)](https://arxiv.org/pdf/2508.19205)
[![ASR 报告](https://img.shields.io/badge/ASR-报告-yellow?logo=arxiv)](https://arxiv.org/pdf/2601.18184)
[![Colab](https://img.shields.io/badge/流式TTS-Colab-green?logo=googlecolab)](https://colab.research.google.com/github/microsoft/VibeVoice/blob/main/demo/VibeVoice_colab.ipynb)
[![ASR 演示](https://img.shields.io/badge/ASR-在线体验-6F42C1?logo=gradio)](https://aka.ms/vibevoice-asr)

</div>


<div align="center">
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/microsoft/VibeVoice/raw/main/Figures/VibeVoice_logo_white.png">
  <img src="https://github.com/microsoft/VibeVoice/raw/main/Figures/VibeVoice_logo.png" alt="VibeVoice Logo" width="300">
</picture>
</div>

<div align="left">

<h3>📰 最新动态</h3>

<strong>2026-03-06：🚀 VibeVoice ASR 已纳入 <a href="https://github.com/huggingface/transformers/releases/tag/v5.3.0">Transformers 正式发布版</a>！现在可以通过 Hugging Face Transformers 库直接使用我们的语音识别模型，轻松集成到您的项目中。</strong>

<strong>2026-01-21：📣 我们开源了 <a href="https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-asr.md"><strong>VibeVoice-ASR</strong></a>，一个统一的语音转文本模型，可在单次处理中处理长达 60 分钟的长音频，生成包含"谁"（说话人）、"何时"（时间戳）和"说了什么"（内容）的结构化转录，并支持用户自定义上下文。在 [在线体验](https://aka.ms/vibevoice-asr) 中试用</strong>。
- ⭐️ VibeVoice-ASR 原生支持多语言，覆盖 50 多种语言——查看[支持的语言列表](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-asr.md#language-distribution)了解详情。
- 🔥 VibeVoice-ASR [微调代码](https://github.com/microsoft/VibeVoice/blob/main/finetuning-asr/README.md)现已发布！
- ⚡️ 现已支持 **vLLM 推理**，可实现更快的推理速度；详见 [vllm-asr](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-vllm-asr.md)。
- 📑 [VibeVoice-ASR 技术报告](https://arxiv.org/pdf/2601.18184)已发布。

2025-12-16：📣 我们为 <a href="https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-realtime-0.5b.md"><strong>VibeVoice‑Realtime‑0.5B</strong></a> 新增了实验性语音角色，包括九种语言（德语、法语、意大利语、日语、韩语、荷兰语、波兰语、葡萄牙语、西班牙语）的多语言语音以及 11 种不同风格的英语语音。[立即体验](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-realtime-0.5b.md#optional-more-experimental-voices)。更多语音类型将陆续添加。

2025-12-03：📣 我们开源了 <a href="https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-realtime-0.5b.md"><strong>VibeVoice‑Realtime‑0.5B</strong></a>，一个支持**流式文本输入**和**鲁棒长文本语音生成**的实时文本转语音模型。在 [Colab](https://colab.research.google.com/github/microsoft/VibeVoice/blob/main/demo/vibevoice_realtime_colab.ipynb) 上体验。


2025-09-05：VibeVoice 是一个旨在推动语音合成社区协作的开源研究框架。发布后，我们发现该工具存在与声明用途不一致的使用情况。由于负责任地使用 AI 是微软的指导原则之一，我们已从此仓库移除 VibeVoice-TTS 代码。


2025-08-25：📣 我们开源了 <a href="https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-tts.md"><strong>VibeVoice-TTS</strong></a>，一个长文本多说话人文本转语音模型，可合成长达 90 分钟、最多 4 个不同说话人的语音。

</div>

## 概述

VibeVoice 是一系列**开源前沿语音 AI 模型**，涵盖文本转语音（TTS）和自动语音识别（ASR）模型。

VibeVoice 的核心创新在于其使用连续语音分词器（声学分词器和语义分词器），以超低帧率 **7.5 Hz** 运行。这些分词器在高效保留音频保真度的同时，显著提升了处理长序列的计算效率。VibeVoice 采用[下一 token 扩散](https://arxiv.org/abs/2412.08635)框架，利用大语言模型（LLM）理解文本上下文和对话流程，并使用扩散头生成高保真声学细节。

更多信息、演示和示例，请访问我们的[项目主页](https://microsoft.github.io/VibeVoice)。


<div align="center">

| 模型 | 权重 | 快速体验 |
|-------|------|---------|
| VibeVoice-ASR-7B | [HF 链接](https://huggingface.co/microsoft/VibeVoice-ASR) | [在线体验](https://aka.ms/vibevoice-asr) |
| VibeVoice-TTS-1.5B | [HF 链接](https://huggingface.co/microsoft/VibeVoice-1.5B) | 已禁用 |
| VibeVoice-Realtime-0.5B | [HF 链接](https://huggingface.co/microsoft/VibeVoice-Realtime-0.5B) | [Colab](https://colab.research.google.com/github/microsoft/VibeVoice/blob/main/demo/vibevoice_realtime_colab.ipynb) |

</div>

## 模型

### 1. 📖 [VibeVoice-ASR](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-asr.md) - 长音频语音识别

**VibeVoice-ASR** 是一个统一的语音转文本模型，可在单次处理中处理长达 **60 分钟的长音频**，生成包含**"谁"（说话人）、"何时"（时间戳）和"说了什么"（内容）**的结构化转录，并支持**自定义热词**。

- **🕒 60 分钟单次处理**：
  与将音频切分为短片段（通常会丢失全局上下文）的传统 ASR 模型不同，VibeVoice ASR 可在 64K token 长度内接收长达 **60 分钟**的连续音频输入。这确保了整个小时内一致的说话人追踪和语义连贯性。

- **👤 自定义热词**：
  用户可以提供自定义热词（例如特定名称、专业术语或背景信息）来引导识别过程，显著提高领域特定内容的准确性。

- **📝 丰富转录（谁、何时、说了什么）**：
  模型同时执行 ASR、说话人分离和时间戳标注，生成指示*谁*在*何时*说了*什么*的结构化输出。

[📖 文档](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-asr.md) | [🤗 Hugging Face](https://huggingface.co/microsoft/VibeVoice-ASR) | [🎮 在线体验](https://aka.ms/vibevoice-asr) | [🛠️ 微调](https://github.com/microsoft/VibeVoice/blob/main/finetuning-asr/README.md) | [📊 论文](https://github.com/microsoft/VibeVoice/blob/main/docs/VibeVoice-ASR-Report.pdf)


<p align="center">
  <img src="https://github.com/microsoft/VibeVoice/raw/main/Figures/DER.jpg" alt="DER" width="50%"><br>
  <img src="https://github.com/microsoft/VibeVoice/raw/main/Figures/cpWER.jpg" alt="cpWER" width="50%"><br>
  <img src="https://github.com/microsoft/VibeVoice/raw/main/Figures/tcpWER.jpg" alt="tcpWER" width="50%">
</p>


<div align="center" id="vibevoice-asr">

https://github.com/user-attachments/assets/acde5602-dc17-4314-9e3b-c630bc84aefa

</div>
<br>

### 2. 🎙️ [VibeVoice-TTS](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-tts.md) - 长文本多说话人 TTS

**最佳用途**：长对话音频、播客、多说话人对话

- **⏱️ 90 分钟长文本生成**：
  可在单次处理中合成长达 **90 分钟**的对话/单人语音，在整个过程中保持说话人一致性和语义连贯性。

- **👥 多说话人支持**：
  在单次对话中支持最多 **4 个不同的说话人**，具有自然的轮替和跨长对话的说话人一致性。

- **🎭 富有表现力的语音**：
  生成富有表现力、自然逼真的语音，能够捕捉对话动态和情感细微差别。

- **🌐 多语言支持**：
  支持英语、中文及其他语言。


[📖 文档](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-tts.md) | [🤗 Hugging Face](https://huggingface.co/microsoft/VibeVoice-1.5B) | [📊 论文](https://arxiv.org/pdf/2508.19205)


<div align="center">
  <img src="https://github.com/microsoft/VibeVoice/raw/main/Figures/VibeVoice-TTS-results.jpg" alt="VibeVoice 结果" width="80%">
</div>


**英语**
<div align="center">

https://github.com/user-attachments/assets/0967027c-141e-4909-bec8-091558b1b784

</div>


**中文**
<div align="center">

https://github.com/user-attachments/assets/322280b7-3093-4c67-86e3-10be4746c88f

</div>

**跨语言**
<div align="center">

https://github.com/user-attachments/assets/838d8ad9-a201-4dde-bb45-8cd3f59ce722

</div>

**即兴演唱**
<div align="center">

https://github.com/user-attachments/assets/6f27a8a5-0c60-4f57-87f3-7dea2e11c730

</div>


**4 人长对话**
<div align="center">

https://github.com/user-attachments/assets/a357c4b6-9768-495c-a576-1618f6275727

</div>





<br>

### 3. ⚡ [VibeVoice-Streaming](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-realtime-0.5b.md) - 实时流式 TTS

VibeVoice-Realtime 是一个**轻量级实时**文本转语音模型，支持**流式文本输入**和**鲁棒的长文本语音生成**。

- 参数量：0.5B（便于部署）
- 实时 TTS（首次可听延迟约 300 毫秒）
- 流式文本输入
- 鲁棒的长文本语音生成（约 10 分钟）

[📖 文档](https://github.com/microsoft/VibeVoice/blob/main/docs/vibevoice-realtime-0.5b.md) | [🤗 Hugging Face](https://huggingface.co/microsoft/VibeVoice-Realtime-0.5B) | [🚀 Colab](https://colab.research.google.com/github/microsoft/VibeVoice/blob/main/demo/vibevoice_realtime_colab.ipynb)


<div align="center" id="generated-example-audio-vibevoice-realtime">

https://github.com/user-attachments/assets/0901d274-f6ae-46ef-a0fd-3c4fba4f76dc

</div>

<br>

## 贡献

请参阅 [CONTRIBUTING.md](https://github.com/microsoft/VibeVoice/blob/main/CONTRIBUTING.md) 了解详细的贡献指南。



## ⚠️ 风险与局限性


尽管已通过多种技术进行优化，模型仍可能产生意外的、有偏见的或不准确的输出。VibeVoice 继承了其基础模型（本版本特指 Qwen2.5 1.5B）产生的任何偏见、错误或遗漏。
深度伪造和虚假信息的风险：高质量的合成语音可能被滥用于创建逼真的虚假音频内容，用于冒充、欺诈或传播虚假信息。用户必须确保转录内容可靠，检查内容准确性，并避免以误导性方式使用生成的内容。用户应以合法方式使用生成的内容和部署模型，完全遵守相关司法管辖区的所有适用法律法规。在分享 AI 生成的内容时，最佳做法是披露 AI 的使用。


我们不建议在未经进一步测试和开发的情况下将 VibeVoice 用于商业或实际应用。本模型仅供研究和开发用途。请负责任地使用。

## Star 历史

![Star 历史图表](https://api.star-history.com/svg?repos=Microsoft/vibevoice&type=date&legend=top-left)
