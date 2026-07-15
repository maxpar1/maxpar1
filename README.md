# Hi, I'm Max 👋

I build AI infrastructure; fine-tuned models, inference systems, and the plumbing that makes them actually work in production.

I'm most interested in the parts most people skip: converting a model to run on-device, debugging why a GPU kernel OOMs at batch 8 but not 7, making a RAG system that doesn't hallucinate. The stuff where there's no Stack Overflow answer and AI tools go in circles trying to figure out.

## What I'm building

### 🧠 [Palimo](https://palimo.dev) - Memory-as-a-Service
A live product. Gives LLM apps structured memory without sending data to OpenAI/Anthropic. Fine-tuned a 4B Gemma model (LoRA) to run memory operations locally via llama.cpp. Multi-tenant SaaS architecture: per-user SQLite isolation, hybrid retrieval (embeddings + entity graph), async commit pipeline. Running in private beta.

`Python · FastAPI · llama.cpp · LoRA fine-tuning · GGUF quantization`

### 🔍 [Iris](https://github.com/maxpar1/iris-project) - Natural Language → SQL
A conversational NL2SQL system that handles real databases. 5-table JOINs across Pagila work on the first try. Two-pass retrieval: embedding-based table ranking with FK graph expansion, then a 20B MLX model generates the SQL. Validation loop repairs bad queries using AST analysis (sqlglot). Intent router decides between SQL, chat, and preference updates.

`Python · MLX · Qwen3-Embedding · sqlglot · PostgreSQL`

### 🎙️ [Voice Assistant](https://github.com/maxpar1/voice-assistant) - On-device Voice AI
iOS app where speech never leaves the phone. Spent a week getting Kokoro-82M to run on CoreML — split the bidirectional LSTMs (pack_padded_sequence isn't traceable), fixed the iSTFT reconstruction, replaced `torch.randn` with Box-Muller noise for determinism. Ships with correlation 0.9826 vs the original PyTorch output. Backend runs a 20B LLM on my Mac, iPhone does TTS + ASR locally.

`Swift · CoreML · Python · WebSocket · Kokoro-82M · JWT (hand-rolled)`

## What I work with

**ML/AI** — PyTorch, LoRA fine-tuning, llama.cpp, MLX, CoreML, GGUF, embedding systems, sentence-transformers, eval harness design

**Backend** — Python (FastAPI, Flask), PostgreSQL, SQLite, DynamoDB, async, WebSockets, hand-rolled auth (PBKDF2 + JWT)

**Infrastructure** — AWS (EC2, Lambda, API Gateway, VPC, CloudFront, RDS), Docker, Linux, Sentry

**Also** — Swift/iOS, CoreML model conversion, WebRTC, sqlglot AST

## How I got here

CS degree from Suffolk University (2024). Before graduating I was the software engineer at a 2-person NYC startup (WADL) — built the full AWS stack, launched a commercial AI product, wired up real-time iOS voice over WebRTC. Before that, AI Gulf Coast — AWS training infrastructure and APIs handling 100K+ writes/day.



## If you want to talk

📧 maxparsons321@gmail.com
