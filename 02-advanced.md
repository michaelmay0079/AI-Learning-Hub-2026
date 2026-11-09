# 02 · 进阶知识（理解它怎么工作）

> **本层目标**：搞懂大模型内部的基本结构与"怎么造出来"，并能用工具做点实事。对应早期路线的"阶段 1–3"。数学仍随用随补。
> 📌 **双主线导航**：本层（进阶知识）为概念/理论主线；要直接动手可直达 [05·动手实操](05-动手实操.md) → [06·实战项目](06-实战项目.md)。

---

## 2.1 编程基础：动手即理解

**目标**：用最轻的方式"摸到"模型——几行 API / Hugging Face，并把提示词当成"编程"的雏形。

**核心要点**
- **Hugging Face `pipeline`**：`pipeline("sentiment-analysis")` 一句话跑通一个模型，零训练。
- **API 调用**：用 DeepSeek / OpenAI API 发一条消息，理解"令牌(token)计费"与"上下文窗口"两个真实边界。
- **提示词即编程雏形**：好提示 = 清晰的"角色 + 任务 + 标准/格式"，本质是在给程序下指令。
- **本地小模型入门**：Ollama 一键跑本地模型，理解"为何 7B 能塞进普通内存"（量化）。

**精选资源**
- 🔴 [Hugging Face LLM Course](https://huggingface.co/learn) — Transformer 原理 + 生态 + 应用。出处：Hugging Face。
- 🔴 [Learn Prompting（含中文）](https://www.learnprompting.org/docs/intro) — 系统提示工程教程。出处：Learn Prompting。
- 🟡 [Ollama](https://ollama.com/) / [llama.cpp](https://github.com/ggml-org/llama.cpp) — 本地推理入门。出处：各自仓库。
- 🟢 实践：用 DeepSeek 或 OpenAI API 写 5 行代码发一条消息，观察 token 计费。

**里程碑自测**
- [ ] 能用 HF `pipeline` 或一次 API 调用跑通一个模型。
- [ ] 能写出"角色+任务+标准"结构的提示词。

---

## 2.2 结构演进：Transformer 主干 + 训练范式

**目标**：理解现代大模型底座，以及"预训练→微调→对齐"三阶段。

**核心要点**
- **完整数据流**：文本 → **Tokenization**（分词/子词） → **Embedding**（词→向量，"意义即几何"） → **Attention（Q/K/V）**（每个词与其他词的相关性加权） → **Transformer 块**（注意力 + 前馈 + 残差/归一化） → 堆叠 N 层 → 输出。
- **为什么需要位置编码**：注意力本身"无顺序感"，需补顺序。
- **三种形态**：Encoder-only(BERT，理解) / Decoder-only(GPT，生成) / Encoder-Decoder(原版，翻译摘要)。
- **三阶段训练**：**预训练**（海量语料学语言） → **微调/指令微调**（学任务） → **对齐 RLHF**（学"有用无害"）。
- **MoE 初探**：混合专家——总参大、激活小（为 03 的 DeepSeek R1 铺垫）。

**精选资源**
- 🔴 [Illustrated Transformer（Jay Alammar）](https://jalammar.github.io/illustrated-transformer/) — 最清晰可视化走读。出处：Jay Alammar。
- 🔴 [3Blue1Brown《Attention》可视化](https://www.youtube.com/@3blue1brown) — 直觉天花板。**需境外网络（YouTube）；中文讲解见 [cn-notes/05](cn-notes/05-3Blue1Brown注意力与GPT-译校.md)**。出处：3Blue1Brown。
- 🔴 [Attention Is All You Need（arXiv:1706.03762）](https://arxiv.org/abs/1706.03762) — 原论文，读摘要与架构图即可。
- 🟡 [Transformer Explained（mlforbeginners）](https://mlforbeginners.com/what-is-a-transformer/) — 一张块图讲透组件。出处：ML for Beginners。
- 🟢 实践：在纸上推演"机器人打开房门，它走进房间"里"它"的注意力应指向谁。

**里程碑自测**
- [ ] 能复述 Token→Embedding→Attention→块→堆叠 的数据流。
- [ ] 能说清 Q/K/V 角色与"为何要位置编码"。
- [ ] 能讲清预训练/微调/RLHF 各自在做什么。

---

## 2.3 用途扩展：RAG / Agent / MCP / 科研落地

**目标**：理解当下最实用的应用范式，并落到你的科研场景。

**核心要点**
- **RAG（检索增强生成）**：向量库 + LLM，先检索再生成，**显著减幻觉、可接私有知识**（如你的文献）。
- **Agent（智能体）**：规划 + 记忆 + 工具调用 + 行动 四模块；能自主拆任务、调工具。
- **Agent 的边界**：Agent ≠ 聊天机器人（只回答）≠ 固定工作流（按预设步骤）。Agent 自主决定"下一步 + 调什么工具"（ReAct：推理→行动→观察 循环）；但生产中更常见的是"少量 agentic 步骤 + 可控工作流"，更易测试与把关。
- **MCP（模型上下文协议，Anthropic 提出）**：让模型安全连接外部工具，类似"AI 的 USB-C"。
- **多模态**：文本/图像/语音联合（概念级，非训练）。
- **科研者落地（重点）**：文献综述辅助、写作/润色、数据分析思路、代码助手、图表解读。

**精选资源**
- 🔴 [CSDN 2025 LLM 路线图（RAG/Agent/MCP 章节）](https://devpress.csdn.net/v1/article/detail/154446381) — 结构化索引。出处：CSDN DevPress。
- 🔴 [llm-universe（Datawhale）](https://github.com/datawhalechina/llm-universe) — 新手做应用/API/知识库/RAG。出处：Datawhale。
- 🟡 [llm-cookbook（Datawhale，吴恩达课中文改编）](https://github.com/datawhalechina/llm-cookbook) — Prompt→RAG→微调全流程。出处：Datawhale。
- 🟡 [科普中国：检索增强生成（RAG）](https://www.kepuchina.cn/article/articleinfo?ar_id=692437&business_type=100) — 通俗讲清向量库 / Embedding / 如何减幻觉。出处：科普中国。
- 🟡 [科普中国：AI 智能体（Agent）是什么](https://www.kepuchina.cn/article/articleinfo?ar_id=689885&business_type=100) — 智能体六模块与闭环，为何是下一代形态。出处：科普中国。
- 🟡 [Model Context Protocol 官方文档](https://modelcontextprotocol.io/) — MCP 标准与"AI 的 USB-C"定位（Anthropic 开放协议）。出处：Anthropic。
- 🟡 [What Are AI Agents?（入门）](https://www.mehulprajapati.com/?p=822) — Agent vs 聊天机器人 vs 工作流、ReAct 模式。出处：Mehul Prajapati。
- 🟢 实践：把一篇你的 PDF 文献喂给支持"上传文档"的助手，问"方法缺陷是什么"，验证检索准确性。

**里程碑自测**
- [ ] 能说清 RAG 为何减幻觉、Agent 与 MCP 在解决什么问题。
- [ ] 已在 ≥1 个科研任务中稳定使用 AI 辅助，并识别出它的幻觉/局限。

---

**本层小结**：完成 02，你已理解大模型"内部怎么工作、怎么造出来、怎么用"。下一步进入 03，看当前最前沿的推理模型范式（锚点 DeepSeek R1）。
