Часть, относящаяся к LLM непосредственно

# 🧠 Large Language Models (LLM) Module

Модуль посвящен полному жизненному циклу больших языковых моделей. Структура папок отражает **хронологическую и логическую эволюцию** разработки LLM.

## 📂 Структура модуля

Все материалы (статьи, код, данные) находятся в директории `papers/` и сгруппированы по следующей логике:

### 🔹 I. Вход и Фундамент

* **`00_The_Guidebook_&_Roadmap`**: Стратегические карты развития, скиллсеты (Anthropic, HF). Читать в первую очередь для понимания масштаба.
* **`02_Model_Backbones`**: "Железо" моделей.
  * *Transformer Evolution:* Классика (GPT, Llama).
  * *Post-Transformer:* Попытки убить квадратичную сложность (Mamba, RWKV, Linear Attention).

### 🔹 II. Данные (Критический слой)

* **`01_Data_Centric_AI`**: Самый важный раздел.
  * *Pretraining:* На чем учить базу (FineWeb, The Pile).
  * *Synthetic:* Как генерировать данные (Cosmopedia, Magpie).
  * *Filtering:* Очистка и дедупликация.
  * *Instruction Tuning:* Код и пайплайны (UltraChat) для превращения "дописывалки текста" в чат-бота.

### 🔹 III. Мышление и Агенты (SOTA)

* **`03_Reasoning_Architectures`**: System 2 Thinking. Модели, которые "думают" (CoT, ToT, DeepSeek-R1).
* **`04_Agentic_Systems_&_MCP`**: Выход во внешний мир. Протоколы (MCP), использование инструментов (Toolformer), автономные агенты.

### 🔹 IV. Инженерия

* **`05_Memory_&_Context`**: RAG, длинный контекст (RoPE, Linear Biases).
* **`06_Engineering_&_Tuning`**: Оптимизация обучения (LoRA, QLoRA, Quantization).
* **`07_Benchmarks_&_Evals`**: Как измерять интеллект (LLM-as-a-Judge, Arena).

---

👉 **С чего начать?** Перейдите к файлу [`HOW_TO_READ.md`](./HOW_TO_READ.md) для получения пошагового алгоритма обучения.

---

Структура раздела:

```md
llm_useful_info/
├── llm
│   ├── papers
│   │   ├── 00_The_Guidebook_&_Roadmap
│   │   │   ├── [claude-scientific-skills](https://github.com/K-Dense-AI/claude-scientific-skills)
│   │   │   ├── AI Engineering Guidebook.pdf
│   │   │   ├── hf-skills-training.md
│   │   │   ├── README_Reading_Order.md
│   │   │   ├── the-smol-training-playbook-the-secrets-to-building-world-class-llms.pdf
│   │   │   └── UAF_blog_post_links.md
│   │   ├── 01_Data_Centric_AI
│   │   │   ├── 01_Pretraining_Corpora
│   │   │   │   ├── Colossal Clean Crawled Corpus.pdf
│   │   │   │   ├── The FineWeb Datasets.pdf
│   │   │   │   ├── The Pile.pdf
│   │   │   │   └── The RefinedWeb Dataset.pdf
│   │   │   ├── 02_Data_Filtering_Quality
│   │   │   │   ├── Deduplicating Training Data Makes Language Models Better.pdf
│   │   │   │   ├── Dolma.pdf
│   │   │   │   └── Quality is All You Need.pdf
│   │   │   ├── 03_Synthetic_Data
│   │   │   │   ├── cosmopedia.md
│   │   │   │   ├── Magpie.pdf
│   │   │   │   ├── Textbooks Are All You Need II.pdf
│   │   │   │   └── Textbooks Are All You Need.pdf
│   │   │   └── 04_Instruction_Tuning_Data
│   │   │       ├── UltraChat
│   │   │       │   ├── data
│   │   │       │   │   ├── split_long.py
│   │   │       │   │   ├── tmp.py
│   │   │       │   │   ├── ultra_eval.json
│   │   │       │   │   └── vllm_chatloop
│   │   │       │   ├── figures
│   │   │       │   │   ├── alpaca.png
│   │   │       │   │   ├── compare_ultra.jpg
│   │   │       │   │   ├── figure.png
│   │   │       │   │   ├── meta_topic.png
│   │   │       │   │   ├── ultra-process.png
│   │   │       │   │   ├── ultra_logo.png
│   │   │       │   │   └── wizard_test.jpg
│   │   │       │   ├── paper
│   │   │       │   │   └── UltraFuser-paper.pdf
│   │   │       │   ├── train
│   │   │       │   │   ├── train_legacy
│   │   │       │   │   │   ├── template
│   │   │       │   │   │   │   └── template.txt
│   │   │       │   │   │   ├── requirements.txt
│   │   │       │   │   │   ├── train.py
│   │   │       │   │   │   └── ultrachat_dataset.py
│   │   │       │   │   ├── requirements.txt
│   │   │       │   │   ├── train_bm.py
│   │   │       │   │   └── ultrachat_dataset.py
│   │   │       │   ├── UltraLM
│   │   │       │   │   ├── util
│   │   │       │   │   │   └── inference.py
│   │   │       │   │   ├── chat_cli.sh
│   │   │       │   │   ├── inference_cli.py
│   │   │       │   │   ├── recover.sh
│   │   │       │   │   └── weight_diff.py
│   │   │       │   ├── LICENSE
│   │   │       │   └── README.md
│   │   │       ├── Orca Progressive Learning.pdf
│   │   │       └── Self-Instruct.pdf
│   │   ├── 02_Model_Backbones
│   │   │   ├── 01_Transformer_Evolution & foundations core
│   │   │   │   ├── Attention is all you need.pdf
│   │   │   │   ├── Gemini 1.5 Unlocking multimodal understanding.pdf
│   │   │   │   ├── gpt-1.pdf
│   │   │   │   ├── GPT-4.pdf
│   │   │   │   ├── Language Models are Few-Shot Learners.pdf
│   │   │   │   ├── Large Language Models A Survey.pdf
│   │   │   │   ├── Mixtral of Experts.pdf
│   │   │   │   ├── Scaling Laws for Neural Language Models.pdf
│   │   │   │   ├── Switch Transformers Scaling to Trillion Parameter Models with Simple and Efficient Sparsity.pdf
│   │   │   │   ├── The Llama 3 Herd of Models.pdf
│   │   │   │   └── Training Compute-Optimal Large Language Models.pdf
│   │   │   └── 02_Post_Transformer_&_SSM
│   │   │       ├── 01_Origins_Linear_Attn
│   │   │       │   ├── Attention Free Transformer.pdf
│   │   │       │   ├── Linear Attention Mechanism.pdf
│   │   │       │   └── RWKV Reinventing RNNs for the Transformer Era.pdf
│   │   │       ├── 02_State_Space_Models
│   │   │       │   ├── Efficiently Modeling Long Sequences with Structured State Spaces.pdf
│   │   │       │   ├── Mamba-1. Linear-Time Sequence Modeling with Selective State Spaces.pdf
│   │   │       │   ├── Mamba-3 Technical Report.pdf
│   │   │       │   ├── Mamba-3D.pdf
│   │   │       │   └── Transformers are SSMs (Mamba-2).pdf
│   │   │       └── 03_Hybrid_Architectures
│   │   │           ├── Griffin Mixing Gated Linear Recurrences with Local Attention.pdf
│   │   │           ├── Jamba A Hybrid Transformer-Mamba Language Model.pdf
│   │   │           ├── RecurrentGemma.pdf
│   │   │           └── Zamba A Compact 7B SSM-Transformer Hybrid.pdf
│   │   ├── 03_Reasoning_Architectures
│   │   │   ├── 01_Hierarchical_Reasoning
│   │   │   │   ├── Hierarchical Reasoning Model.pdf
│   │   │   │   ├── Quiet-STaR.pdf
│   │   │   │   └── Towards System 2 Reasoning in LLMs.pdf
│   │   │   ├── 02_Reinforcement_Thinking
│   │   │   │   ├── DeepSeek-R1.pdf
│   │   │   │   ├── Graph of Thoughts Solving Elaborate Problems with Large Language Models.pdf
│   │   │   │   ├── Let’s Verify Step by Step.pdf
│   │   │   │   ├── Manifold-Constrained Hyper-Connections.pdf
│   │   │   │   ├── Model-First Reasoning LLM Agents.pdf
│   │   │   │   ├── RL_base.pdf
│   │   │   │   └── Tree of Thoughts Deliberate Problem Solving.pdf
│   │   │   └── 03_Alignment_History
│   │   │       ├── Constitutional AI.pdf
│   │   │       ├── DPO.pdf
│   │   │       └── RLHF.pdf
│   │   ├── 04_Agentic_Systems_&_MCP
│   │   │   ├── 01_Protocols
│   │   │   │   └── MCP.pdf
│   │   │   ├── 02_Agentic_Frameworks
│   │   │   │   ├── OPENHANDS.pdf
│   │   │   │   ├── SWE-agent Agent-Computer Interfaces.pdf
│   │   │   │   └── Toolformer Language Models Can Teach Themselves to Use Tools.pdf
│   │   │   └── 03_Environment
│   │   │       └── VOYAGER.pdf
│   │   ├── 05_Memory_&_Context
│   │   │   ├── LEANN-main.zip
│   │   │   ├── LEANN.pdf
│   │   │   ├── Retrieval-Augmented Generation.pdf
│   │   │   ├── RoPE.pdf
│   │   │   └── TRAIN SHORT, TEST LONG ATTENTION WITH LINEAR BIASES ENABLES INPUT LENGTH EXTRAPOLATION.pdf
│   │   ├── 06_Engineering_&_Tuning
│   │   │   ├── finLORA.pdf
│   │   │   ├── LoRA.pdf
│   │   │   ├── MEA.zip
│   │   │   ├── QLORA Efficient Finetuning of Quantized LLMs.pdf
│   │   │   └── Разработка LLM с нуля.rar
│   │   ├── 07_Benchmarks_&_Evals
│   │   │   ├── ARC-AGI.pdf
│   │   │   ├── Beyond the Imitation Game.pdf
│   │   │   ├── Chatbot Arena An Open Platform for Evaluating LLMs by Human Preference.pdf
│   │   │   ├── LLM-as-a-Judge.pdf
│   │   │   └── SWE-BENCH CAN LANGUAGE MODELS RESOLVE real-world github issues.pdf
│   │   ├── xx_prompting
│   │   │   ├── Chain-of-Thought Prompting Elicits Reasoning.pdf
│   │   │   ├── REACT SYNERGIZING REASONING AND ACTING IN LM.pdf
│   │   │   └── The Prompt Report A Systematic Survey of Prompt Engineering.pdf
│   │   └── readme.md
│   ├── Supporting_Resources
│   │   ├── External_Book_CS249R
│   │   │   ├── [cs249r_book](cs249r_book)
│   │   │   └── book_link.md
│   │   ├── LEANN_Repo_Link.md
│   │   ├── Mamba_SSM_Repo_Link.md
│   │   ├── Stanford_CME295_link.md
│   │   └── VLA_blogpost_link.md
│   └── readme.md
├── PROJECT_STRUCTURE.md
└── README.md

```
