# awesome-local-ai

> Curated list of AI tools that run **100% on your machine** — no cloud, no telemetry, no "local-ish" setups that secretly phone home.

Maintained by [Brethof AI](https://brethof.ai). Companion to
[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt) and
[awesome-private-ai](https://github.com/BrethofAI/awesome-private-ai).

## Why this list exists

The phrase "local-first" has been stretched to mean almost anything in
2026. Lots of tools advertise on-device AI but then call out to remote
APIs for "complex" prompts, sync your data to a "private" cloud bucket,
or ship telemetry that re-introduces every privacy problem the local
mode was meant to solve.

This list applies a strict rule: **the tool must perform inference on
hardware you own and not transmit prompts, embeddings, or audio off
that hardware during normal use.** Optional cloud features (like model
download or update checks) are fine; mandatory ones disqualify.

Where a tool is partially-local (e.g. ships a fully-local mode but
defaults to cloud), we say so explicitly. Every link is checked — a
CI-style sweep cuts entries whose URL 404s.

## Inclusion rules

To be listed:

- It runs on the user's own hardware — inference on a CPU, GPU, NPU or
  local accelerator, or a component of a local AI stack (vector store,
  memory, embeddings, training).
- No mandatory account just to use it offline.
- Source code or signed binaries — verifiable provenance.
- A real artefact you can install today, not a "coming soon" page.

New or small is fine: we don't turn a tool away for being young or
little-known. Every entry is labelled honestly instead — 🆕 marks a
listing from the last 60 days — and our weekly check removes anything that
stops working or goes six months without a release, commit or merged PR.
We decline only tools with nothing real to point at, misleading claims,
or no local mode at all.

## Legend

- 🐧 Linux · 🪟 Windows · 🍎 macOS · 📱 iOS / Android · 🌐 Web (in-browser)
- 🔓 open source · 🔒 closed source
- 🆓 free for personal · 💰 paid · 🆓💰 free + paid tiers
- 🐍 Python · 🦀 Rust · 🐹 Go · ⚙️ C/C++ · 🟦 TypeScript / JS
- 🆕 new — listed in the last 60 days

## Contents

- [Inference Runtimes](#inference-runtimes) (13)
- [Desktop Chat Apps](#desktop-chat-apps) (3)
- [Voice — Speech-to-Text](#voice-—-speech-to-text) (11)
- [Voice — Text-to-Speech](#voice-—-text-to-speech) (6)
- [Image Generation](#image-generation) (7)
- [Video Generation](#video-generation) (3)
- [Code Assistants](#code-assistants) (5)
- [Local Agents](#local-agents) (5)
- [Vector Databases](#vector-databases) (5)
- [Embeddings](#embeddings) (3)
- [Training & Fine-tuning](#training--fine-tuning) (5)
- [Local Search & RAG](#local-search--rag) (5)
- [Operating Systems Tuned for AI](#operating-systems-tuned-for-ai) (2)
- [Hardware-Specific Runtimes](#hardware-specific-runtimes) (4)

<!-- The list below is generated from entries/*.yaml by scripts/gen_awesome_readme.py. Edit the YAML, not this section. -->

## Inference Runtimes

Engines that load LLMs, vision models, and other neural networks for inference on your hardware.

- **[ExLlamaV3](https://github.com/turboderp-org/exllamav3)** — 🆕 🐧 🪟 🔓 🆓 🐍  
  Fast quantised-LLM inference on consumer NVIDIA GPUs; successor to ExLlamaV2 (archived by its author). Serve it with [TabbyAPI](https://github.com/theroyallab/tabbyAPI).
- **[Jan](https://jan.ai)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  Open-source ChatGPT alternative. Bundles llama.cpp + a clean UI.
- **[KoboldCpp](https://github.com/LostRuins/koboldcpp)** — 🐧 🪟 🍎 🔓 🆓 ⚙️  
  Single-binary llama.cpp wrapper with KoboldAI UI for chat, story-writing, RP.
- **[llama.cpp](https://github.com/ggml-org/llama.cpp)** — 🐧 🪟 🍎 🔓 ⚙️  
  Reference C++ implementation for running LLaMA-family and other transformer models with GGUF quantization. Powers most of the others in this section.
- **[llamafile](https://github.com/mozilla-ai/llamafile)** — 🆕 🐧 🪟 🍎 🔓 🆓 ⚙️  
  Mozilla's one-file LLM: model and llama.cpp runtime in a single executable that runs on Linux, Windows and macOS without an install.
- **[LM Studio](https://lmstudio.ai)** — 🐧 🪟 🍎 🔒 🆓 ⚙️  
  Polished desktop app for discovering, downloading, and running local LLMs. OpenAI-compatible server mode. Free for personal + commercial.
- **[LocalAI](https://localai.io)** — 🐧 🪟 🍎 🔓 🆓 🐹  
  Self-hosted, OpenAI-compatible inference server. Text, image, audio, embeddings — all on your machine.
- **[Mistral.rs](https://github.com/EricLBuehler/mistral.rs)** — 🐧 🪟 🍎 🔓 🆓 🦀  
  Rust LLM inference platform with quantization, vision, MoE, and speculative decoding.
- **[MLC LLM](https://llm.mlc.ai)** — 🐧 🪟 🍎 📱 🌐 🔓 🆓 🐍  
  Compile-once, deploy-anywhere LLM runtime. Targets WebGPU, Vulkan, CUDA, Metal, iOS, and Android from a single source.
- **[Ollama](https://ollama.com)** — 🐧 🪟 🍎 🔓 🆓 🐹  
  Single-binary server with a built-in model library. Pull, run, and swap models with one command.
- **[SGLang](https://sgl-project.github.io)** — 🐧 🔓 🆓 🐍  
  Fast LLM and VLM serving runtime with RadixAttention cache and structured-output support.
- **[TextGen (text-generation-webui)](https://github.com/oobabooga/textgen)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  oobabooga's desktop app for local LLMs, renamed from text-generation-webui. llama.cpp, ExLlamaV3, Transformers and TensorRT-LLM backends; vision and tool-calling.
- **[vLLM](https://docs.vllm.ai)** — 🐧 🔓 🆓 🐍  
  High-throughput inference engine with PagedAttention. Designed for serving, not desktop chat — pair with Open WebUI or LiteLLM.

## Desktop Chat Apps

GUI applications wrapping a local runtime in a chat interface.

- **[Anything LLM](https://anythingllm.com)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  Workspace-style chat with built-in RAG. Works fully offline with a local LLM provider.
- **[Msty Studio](https://msty.ai)** — 🐧 🪟 🍎 🔒 🆓 🟦  
  Desktop chat with branching conversations and parallel-model comparison; local engines (Ollama, llama.cpp, MLX) are in the free tier.
- **[Open WebUI](https://openwebui.com)** — 🐧 🪟 🍎 🌐 🔓 🆓 🐍  
  Self-hosted "ChatGPT clone" of the open-source world. Pair with Ollama or any OpenAI-compatible local server.

## Voice — Speech-to-Text

- **[Brethof Voice Pro](https://brethof.ai/voice/)** — 🐧 🪟 🔒 💰  
  Voice-to-text, translation and subtitles, all on your own computer: transcription in 30 languages plus 22 Chinese dialects (Qwen3-ASR 0.6B / 1.7B), offline translation across 38 languages (Hunyuan MT2), text / SRT / VTT subtitles whose timings survive translation, and a voice keyboard that types into any app — the transcript or its translation. Listens to the microphone, a file, or system audio; runs on CPU or any Vulkan 1.2+ GPU (NVIDIA, AMD, Intel). Voice training from your own corrections and an MCP server for agents come with a paid licence; 14-day trial. Network use is a licence check, an update check and the model downloads you start — no audio, no text. Disclosure: maintained by us.
- **[Dictámelo](https://github.com/sarrazola/dictamelo)** — 🆕 🪟 🍎 🔓 🆓 🦀  
  Hold-to-talk dictation into any text field, with local Whisper, Parakeet v3 and Canary models that work offline after one download, no account or API key. Cloud transcription and AI clean-up are optional extras, off the offline path.
- **[Handy](https://github.com/cjpais/Handy)** — 🆕 🐧 🪟 🍎 🔓 🆓 🦀  
  Free, open-source push-to-talk dictation into any app, working completely offline with Whisper or Parakeet models.
- **[Moonshine](https://github.com/moonshine-ai/moonshine)** — 🆕 🐧 🪟 🍎 📱 🔓 🆓 🐍  
  Very low-latency streaming speech-to-text for on-device use; no account or API key. Code and default models MIT (legacy non-English models are non-commercial).
- **[NVIDIA Parakeet TDT 0.6B v3](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v3)** — 🆕 🐧 🪟 🍎 🔓 🆓 🐍  
  Fast multilingual ASR model (CC-BY-4.0). Run it locally with [onnx-asr](https://github.com/istupakov/onnx-asr), [parakeet-mlx](https://github.com/senstella/parakeet-mlx) or NVIDIA NeMo.
- **[OpenAI Whisper](https://github.com/openai/whisper)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Reference Python implementation. Accurate but slower than the C++ ports; useful when you need the exact research behaviour.
- **[RealtimeSTT](https://github.com/KoljaB/RealtimeSTT)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Low-latency streaming wrapper around faster-whisper for live dictation pipelines.
- **[VibeVoice](https://github.com/microsoft/VibeVoice)** — 🆕 🐧 🔓 🆓 🐍  
  Microsoft's MIT-licensed voice models: VibeVoice-ASR (long-form transcription with speaker labels, 50+ languages, streaming variant) and a realtime 0.5B TTS.
- **[Vosk](https://alphacephei.com/vosk/)** — 🐧 🪟 🍎 📱 🔓 🆓 🐍  
  Lightweight offline speech recognizer with 20+ language models. Real-time on CPU.
- **[Whisper.cpp](https://github.com/ggml-org/whisper.cpp)** — 🐧 🪟 🍎 📱 🔓 🆓 ⚙️  
  C++ port of OpenAI Whisper with GGUF quantization. Runs on CPU, Metal, CUDA, Vulkan.
- **[WhisperX](https://github.com/m-bain/whisperX)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  faster-whisper plus forced alignment, voice-activity detection, and speaker diarization.

## Voice — Text-to-Speech

- **[Chatterbox](https://github.com/resemble-ai/chatterbox)** — 🆕 🐧 🔓 🆓 🐍  
  Resemble AI's MIT-licensed voice-cloning TTS family: Multilingual (0.5B), Turbo (350M, supports tags like [laugh]) and Nano (110M, CPU).
- **[Coqui TTS (idiap fork)](https://github.com/idiap/coqui-ai-TTS)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  The maintained fork of the Coqui TTS toolkit (the original repo is unmaintained). Multiple architectures (VITS, XTTS) and voice cloning. pip install coqui-tts.
- **[Kokoro](https://huggingface.co/hexgrad/Kokoro-82M)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Tiny 82M-param TTS model (Apache-2.0), surprisingly natural for the size and fine on low-end hardware. Run it with [Kokoro-FastAPI](https://github.com/remsky/Kokoro-FastAPI) (OpenAI-compatible server) or [kokoro-onnx](https://github.com/thewh1teagle/kokoro-onnx).
- **[Kyutai Pocket TTS](https://github.com/kyutai-labs/pocket-tts)** — 🆕 🐧 🪟 🍎 🔓 🆓 🐍  
  Lightweight TTS from Kyutai built to run on a CPU, no GPU PyTorch needed. Code MIT, weights CC-BY-4.0.
- **[Piper](https://github.com/OHF-Voice/piper1-gpl)** — 🐧 🪟 🍎 📱 🔓 🆓 ⚙️  
  Fast neural TTS, dozens of voices and languages, built for Raspberry Pi-class hardware. Development moved from rhasspy/piper (archived) to the Open Home Foundation; now GPL-3.0.
- **[VoxCPM2](https://github.com/OpenBMB/VoxCPM)** — 🆕 🐧 🍎 🔓 🆓 🐍  
  Multilingual TTS with voice design and cloning from OpenBMB; Apache-2.0 code and weights. pip install voxcpm.

## Image Generation

- **[ComfyUI](https://github.com/Comfy-Org/ComfyUI)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Node-graph workflow editor for diffusion models. Powers most modern local image and video pipelines.
- **[Forge Classic / Neo](https://github.com/Haoming02/sd-webui-forge-classic)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  The maintained continuation of lllyasviel's Forge (the original has not moved since mid-2025). Low-VRAM A1111-style UI; the default Neo branch adds newer model support. AGPL-3.0.
- **[InvokeAI](https://invoke.com)** — 🐧 🪟 🍎 🔓 🔒 🆓 💰 🐍  
  Pro-grade SD UI with strong canvas / inpainting tools. Enterprise tier; free local install remains open source.
- **[Mold](https://github.com/utensils/mold)** — 🆕 🐧 🍎 🔓 🆓 🦀  
  CLI-native local image, video and 3D generation in Rust (Candle, CUDA/Metal), with an MCP server, for people, scripts and agents.
- **[Radiant Canvas (formerly Krealize)](https://radiantbeargames.com/radiant-canvas)** — 🆕 🍎 🔒 🆓 💰  
  Native Mac image generator and editor running open models (FLUX.2 Klein, Krea 2, Qwen Image Edit, Z-Image and more) entirely on Apple silicon via MLX. No account, no telemetry. Closed source; free tier includes every model, PRO adds formats and advanced nodes. macOS 26.2+.
- **[SD.Next](https://github.com/vladmandic/sdnext)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  All-in-one fork of A1111 with broader backend support (Diffusers, ONNX, ROCm).
- **[SwarmUI](https://github.com/mcmonkeyprojects/SwarmUI)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  Modular UI built on top of ComfyUI. User-friendly mode out of the box, full node-graph available when you need it.

## Video Generation

- **[ComfyUI + LTX Video](https://github.com/Comfy-Org/ComfyUI)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  ComfyUI nodes drive Lightricks LTX video models for text-to-video and image-to-video generation. The chunked-loop pattern (released in our [comfyui-workflows](https://github.com/BrethofAI/comfyui-workflows)) produces longer outputs than vanilla LTX allows.
- **[NanoAvatar](https://github.com/wpydcr/NanoAvatar)** — 🆕 📱 🔓 🆓  
  Audio-driven talking avatars generated on an Android phone; Experience mode runs fully offline, no account or API key. Code MIT; the lip-sync weights and default avatar are CC BY-NC 4.0 (non-commercial).
- **[Wan2GP](https://github.com/deepbeepmeep/Wan2GP)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Stripped-down Wan2.2 video pipeline for low-VRAM consumer GPUs.

## Code Assistants

- **[Aider](https://aider.chat)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Terminal pair-programming. Bring-your-own-LLM via LiteLLM — run with Ollama or any OpenAI-compatible local endpoint.
- **[Continue](https://continue.dev)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  IDE assistant with first-class local-LLM support. Defaults can be set to Ollama / LM Studio. VS Code + JetBrains.
- **[Llama.vim](https://github.com/ggml-org/llama.vim)** — 🐧 🪟 🍎 🔓 🆓 ⚙️  
  Vim plugin that streams llama.cpp completions inline. No cloud.
- **[Tabby](https://tabby.tabbyml.com)** — 🐧 🪟 🍎 🔓 🆓 🦀  
  Self-hosted GitHub Copilot alternative. Local model serving with IDE plugins.
- **[twinny](https://github.com/twinnydotdev/twinny)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  Free local AI extension for VS Code. Chat + autocomplete via Ollama.

## Local Agents

- **[Aider in /architect mode](https://aider.chat/docs/usage/modes.html)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Aider's planning mode separates "decide" and "edit" steps; works well with strong local reasoning models.
- **[Continue Agent mode](https://docs.continue.dev/agent/how-to-use-it)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  Agentic editing flow inside Continue. Pair with a local model for fully-offline coding agents.
- **[Hyperconsciousness (hc)](https://github.com/louis030195/hyperconsciousness)** — 🆕 🐧 🪟 🍎 🔓 🆓 🦀  
  Encrypted, append-only knowledge store for local agents (Rust CLI, MIT) with scoped, expiring grants over MCP/HTTP; no hosted service required, device sync optional. Developer alpha with no independent audit yet; installer builds auto-update from GitHub by default.
- **[Open Interpreter](https://github.com/openinterpreter/openinterpreter)** — 🐧 🪟 🍎 🔓 🆓 🦀  
  Rewritten in 2026 as a Rust coding agent (a fork of OpenAI's Codex) for open models. Fully local with --oss and Ollama or LM Studio as the provider.
- **[Tree Ring Memory](https://github.com/TerminallyLazy/Tree-Ring-Memory)** — 🆕 🐧 🍎 🔓 🆓 🦀  
  Local-first memory for coding agents: a Rust CLI/TUI with project-scoped SQLite/FTS recall, audit and forgetting. No account, no cloud service.

## Vector Databases

- **[Chroma](https://www.trychroma.com)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Embedding database designed for local-first usage. SQLite-style single-file or client/server.
- **[Faiss](https://github.com/facebookresearch/faiss)** — 🐧 🪟 🍎 🔓 🆓 ⚙️  
  Library for similarity search. The retrieval engine inside many of the others.
- **[LanceDB](https://lancedb.com)** — 🐧 🪟 🍎 🔓 🆓 🦀  
  Embedded, columnar vector DB. Single-file, no server.
- **[Qdrant](https://qdrant.tech)** — 🐧 🪟 🍎 🔓 🆓 🦀  
  High-performance vector DB. Self-host the open-source binary.
- **[Weaviate](https://weaviate.io)** — 🐧 🪟 🍎 🔓 🆓 🐹  
  Hybrid (vector + keyword) DB. Self-host the OSS distribution; cloud is optional.

## Embeddings

- **[BGE](https://github.com/FlagOpen/FlagEmbedding)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  BAAI's BGE family. Strong English + multilingual variants. Run via llama.cpp, sentence-transformers, or fastembed.
- **[fastembed](https://github.com/qdrant/fastembed)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Lightweight CPU-friendly embedding library by Qdrant.
- **[Sentence Transformers](https://www.sbert.net)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Reference Python library for sentence + paragraph embeddings.

## Training & Fine-tuning

- **[Axolotl](https://github.com/axolotl-ai-cloud/axolotl)** — 🐧 🔓 🆓 🐍  
  Config-driven fine-tuning framework. LoRA, QLoRA, full fine-tunes.
- **[diffusion-pipe](https://github.com/tdrussell/diffusion-pipe)** — 🐧 🔓 🆓 🐍  
  Pipeline-parallel trainer for diffusion models. Multi-GPU LoRA on large image / video models.
- **[MLX](https://github.com/ml-explore/mlx)** — 🍎 🔓 🆓 🐍  
  Apple's native ML framework for Apple Silicon. Train and infer on M-series Macs without CUDA workarounds.
- **[Ostris ai-toolkit](https://github.com/ostris/ai-toolkit)** — 🐧 🪟 🔓 🆓 🐍  
  LoRA training UI for Flux, SD3, SDXL, LTX. Works on consumer hardware.
- **[Unsloth](https://unsloth.ai)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Fine-tune LLMs 2× faster with 70% less VRAM than reference HuggingFace pipelines.

## Local Search & RAG

- **[Anything LLM](https://anythingllm.com)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  Self-hosted workspace tool with integrated RAG. Listed twice intentionally — strong both as a chat app and a RAG layer.
- **[LlamaIndex](https://www.llamaindex.ai)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Toolkit for building RAG pipelines. Works fully offline with local models + vector DBs.
- **[PrivateGPT](https://github.com/zylon-ai/private-gpt)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Ingest documents locally and query them with an offline LLM.
- **[SearXNG](https://github.com/searxng/searxng)** — 🐧 🪟 🍎 🔓 🆓 🐍  
  Self-hosted meta-search engine. Pair with a local LLM for an offline Perplexity-style assistant.
- **[Vane (formerly Perplexica)](https://github.com/ItzCrazyKns/Vane)** — 🐧 🪟 🍎 🔓 🆓 🟦  
  Privacy-focused AI answering engine that runs entirely on your own hardware: SearXNG search plus a local LLM via Ollama.

## Operating Systems Tuned for AI

The two distros that come ready for local AI out of the box. The full, ranked comparison lives in [awesome-linux-for-ai](https://github.com/BrethofAI/awesome-linux-for-ai).

- **[CachyOS](https://cachyos.org)** — 🐧 🔓 🆓  
  Arch-based desktop distro with a tuned kernel and recent NVIDIA / AMD drivers. Sane out-of-the-box for new GPUs (Blackwell, RDNA 4).
- **[Pop!_OS](https://pop.system76.com)** — 🐧 🔓 🆓  
  System76's NVIDIA-friendly desktop distro. ISO ships with proprietary drivers for plug-and-play GPU work.

## Hardware-Specific Runtimes

- **[MLX](https://github.com/ml-explore/mlx)** — 🍎 🔓 🆓 🐍  
  Apple Silicon-native ML library. Already listed under training; it also ships an inference runtime competitive with llama.cpp on M-series.
- **[NVIDIA TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM)** — 🐧 🪟 🔒 🆓 🐍  
  NVIDIA's optimised LLM runtime for their data-center and consumer GPUs. Closed-weights binary; fastest CUDA path for many models.
- **[OpenVINO](https://github.com/openvinotoolkit/openvino)** — 🐧 🪟 🍎 🔓 🆓 ⚙️  
  Intel's inference toolkit. CPU, iGPU, dGPU (Arc), and NPU support for Intel laptops.
- **[ROCm + llama.cpp HIP](https://github.com/ggml-org/llama.cpp)** — 🐧 🪟 🍎 🔓 ⚙️  
  AMD GPU inference path. Llama.cpp's HIP backend now reaches CUDA parity on RDNA 3/4 in many workloads.

## Related work

- **[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt)** — Tools that publish `llms.txt` for agent discovery.
- **[awesome-private-ai](https://github.com/BrethofAI/awesome-private-ai)** — Privacy-first AI more broadly (some on this list, plus privacy-respecting cloud).
- **[awesome-mcp-servers](https://github.com/BrethofAI/awesome-mcp-servers)** — MCP servers, many of which sit happily next to a local LLM.
- **[awesome-ai-minefield](https://github.com/BrethofAI/awesome-ai-minefield)** — License + ToS analysis for the models you'll run locally.
- **[awesome-linux-for-ai](https://github.com/BrethofAI/awesome-linux-for-ai)** — Linux distros tuned for the AI workstations these tools live on.
- **[comfyui-workflows](https://github.com/BrethofAI/comfyui-workflows)** — Curated, working ComfyUI workflows for local image / video generation.

## Contributing

Open an issue with the tool name, repo or homepage URL, the category it
should land in, and one paragraph on why it's worth listing. Entries live
as one YAML file each under `entries/`; this README is generated from them,
so edit the YAML, not the list above. We do not list tools whose offline
mode is gated behind a paid plan.

## License

[MIT](LICENSE).

---

Maintained by **[Brethof AI](https://brethof.ai)** — AI tools built for
people who take their data seriously.
