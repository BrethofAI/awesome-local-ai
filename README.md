# awesome-local-ai

> Curated list of AI tools that run **100% on your machine** — no cloud, no telemetry, no "local-ish" setups that secretly phone home.

Maintained by [Brethof AI](https://brethof.com). Companion to
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
defaults to cloud), we say so explicitly.

## Inclusion rules

To be listed:

- Inference happens on the user's CPU, GPU, NPU, or local accelerator.
- No mandatory account creation just to use the offline mode.
- Source code or signed binaries available — verifiable provenance.
- Maintained: a release, commit, or PR merge in the last 6 months.
- Real artefact (not a "coming soon" landing page).

## Legend

- 🐧 Linux · 🪟 Windows · 🍎 macOS · 📱 iOS / Android · 🌐 Web (in-browser)
- 🔓 open source · 🔒 closed source
- 🆓 free for personal · 💰 paid · 🆓💰 free + paid tiers
- 🐍 Python · 🦀 Rust · 🐹 Go · ⚙️ C/C++ · 🟦 TypeScript / JS

## Contents

- [Inference Runtimes](#inference-runtimes)
- [Desktop Chat Apps](#desktop-chat-apps)
- [Voice — Speech-to-Text](#voice--speech-to-text)
- [Voice — Text-to-Speech](#voice--text-to-speech)
- [Image Generation](#image-generation)
- [Video Generation](#video-generation)
- [Code Assistants](#code-assistants)
- [Local Agents](#local-agents)
- [Vector Databases](#vector-databases)
- [Embeddings](#embeddings)
- [Training & Fine-tuning](#training--fine-tuning)
- [Local Search & RAG](#local-search--rag)
- [Operating Systems Tuned for AI](#operating-systems-tuned-for-ai)
- [Hardware-Specific Runtimes](#hardware-specific-runtimes)

## Inference Runtimes

Engines that load LLMs, vision models, and other neural networks for
inference on your hardware.

- **[llama.cpp](https://github.com/ggml-org/llama.cpp)** — 🐧🪟🍎 🔓 ⚙️
  Reference C++ implementation for running LLaMA-family and other
  transformer models with GGUF quantization. Powers most of the
  others in this section.
- **[Ollama](https://ollama.com)** — 🐧🪟🍎 🔓 🆓 🐹
  Single-binary server with a built-in model library. Pull, run, and
  swap models with one command.
- **[LM Studio](https://lmstudio.ai)** — 🐧🪟🍎 🔒 🆓 ⚙️
  Polished desktop app for discovering, downloading, and running local
  LLMs. OpenAI-compatible server mode. Free for personal + commercial.
- **[GPT4All](https://www.nomic.ai/gpt4all)** — 🐧🪟🍎 🔓 🆓 ⚙️
  Privacy-first desktop chat with curated quantised models. Strong CPU
  performance.
- **[Jan](https://jan.ai)** — 🐧🪟🍎 🔓 🆓 🟦
  Open-source ChatGPT alternative. Bundles llama.cpp + a clean UI.
- **[KoboldCpp](https://github.com/LostRuins/koboldcpp)** — 🐧🪟🍎 🔓 🆓 ⚙️
  Single-binary llama.cpp wrapper with KoboldAI UI for chat,
  story-writing, RP.
- **[vLLM](https://docs.vllm.ai)** — 🐧 🔓 🆓 🐍
  High-throughput inference engine with PagedAttention. Designed for
  serving, not desktop chat — pair with Open WebUI or LiteLLM.
- **[ExLlamaV2](https://github.com/turboderp-org/exllamav2)** — 🐧🪟 🔓 🆓 🐍
  Fast inference for quantised LLMs on consumer NVIDIA GPUs. EXL2
  format outperforms GGUF on the same hardware in many benchmarks.
- **[MLC LLM](https://llm.mlc.ai)** — 🐧🪟🍎📱🌐 🔓 🆓 🐍
  Compile-once, deploy-anywhere LLM runtime. Targets WebGPU, Vulkan,
  CUDA, Metal, iOS, and Android from a single source.
- **[Text Generation WebUI](https://github.com/oobabooga/text-generation-webui)** — 🐧🪟🍎 🔓 🆓 🐍
  Gradio-based web UI for local LLMs. Supports GGUF, GPTQ, AWQ, EXL2.
- **[LocalAI](https://localai.io)** — 🐧🪟🍎 🔓 🆓 🐹
  Self-hosted, OpenAI-compatible inference server. Text, image, audio,
  embeddings — all on your machine.
- **[SGLang](https://sgl-project.github.io)** — 🐧 🔓 🆓 🐍
  Fast LLM and VLM serving runtime with RadixAttention cache and
  structured-output support.
- **[Mistral.rs](https://github.com/EricLBuehler/mistral.rs)** — 🐧🪟🍎 🔓 🆓 🦀
  Rust LLM inference platform with quantization, vision, MoE, and
  speculative decoding.

## Desktop Chat Apps

GUI applications wrapping a local runtime in a chat interface.

- **[Open WebUI](https://openwebui.com)** — 🐧🪟🍎🌐 🔓 🆓 🐍
  Self-hosted "ChatGPT clone" of the open-source world. Pair with
  Ollama or any OpenAI-compatible local server.
- **[Anything LLM](https://anythingllm.com)** — 🐧🪟🍎 🔓 🆓 🟦
  Workspace-style chat with built-in RAG. Works fully offline with a
  local LLM provider.
- **[Msty](https://msty.app)** — 🐧🪟🍎 🔒 🆓 🟦
  Fast desktop chat with branching conversations and parallel-model
  comparison. Free tier covers personal local use.
- **[Faraday](https://faraday.dev)** — 🐧🪟🍎 🔒 🆓 ⚙️
  Local-only character / role-play chat. Bundles inference, no API key
  needed.

## Voice — Speech-to-Text

- **[Whisper.cpp](https://github.com/ggml-org/whisper.cpp)** — 🐧🪟🍎📱 🔓 🆓 ⚙️
  C++ port of OpenAI Whisper with GGUF quantization. Runs on CPU,
  Metal, CUDA, Vulkan.
- **[faster-whisper](https://github.com/SYSTRAN/faster-whisper)** — 🐧🪟🍎 🔓 🆓 🐍
  CTranslate2-based reimplementation. ~4× faster than reference
  Whisper at the same accuracy.
- **[WhisperX](https://github.com/m-bain/whisperX)** — 🐧🪟🍎 🔓 🆓 🐍
  faster-whisper plus forced alignment, voice-activity detection, and
  speaker diarization.
- **[Brethof Voice Pro](https://brethof.com)** — 🐧🪟 🔒 🆓💰 ⚙️
  Desktop dictation app built on Qwen3-ASR + GGUF + llama.cpp. 36
  languages, hotkey-anywhere transcription, file/microphone/system-audio
  input, LoRA personal voice training. 100% offline, no account
  required to transcribe. Disclosure: maintained by us.
- **[Vosk](https://alphacephei.com/vosk/)** — 🐧🪟🍎📱 🔓 🆓 🐍
  Lightweight offline speech recognizer with 20+ language models.
  Real-time on CPU.
- **[RealtimeSTT](https://github.com/KoljaB/RealtimeSTT)** — 🐧🪟🍎 🔓 🆓 🐍
  Low-latency streaming wrapper around faster-whisper for live
  dictation pipelines.
- **[OpenAI Whisper](https://github.com/openai/whisper)** — 🐧🪟🍎 🔓 🆓 🐍
  Reference Python implementation. Accurate but slower than the C++
  ports; useful when you need the exact research behaviour.

## Voice — Text-to-Speech

- **[Piper](https://github.com/rhasspy/piper)** — 🐧🪟🍎📱 🔓 🆓 ⚙️
  Fast neural TTS. ONNX runtime, dozens of voices and languages.
  Designed for Raspberry Pi-class hardware.
- **[Coqui TTS](https://github.com/coqui-ai/TTS)** — 🐧🪟🍎 🔓 🆓 🐍
  Comprehensive TTS toolkit. Multiple architectures (Tacotron, VITS,
  XTTS) and voice cloning.
- **[Bark](https://github.com/suno-ai/bark)** — 🐧🪟🍎 🔓 🆓 🐍
  Multilingual generative audio. Speech, sound effects, and music
  cues from text prompts.
- **[StyleTTS 2](https://github.com/yl4579/StyleTTS2)** — 🐧🪟🍎 🔓 🆓 🐍
  High-fidelity expressive TTS with style transfer. Strong reference
  voice cloning.
- **[Mimic 3](https://github.com/MycroftAI/mimic3)** — 🐧🪟🍎📱 🔓 🆓 🐍
  Mycroft's neural TTS engine. Lightweight, multilingual.
- **[Kokoro](https://github.com/hexgrad/kokoro)** — 🐧🪟🍎 🔓 🆓 🐍
  Tiny ~80M-param TTS model, surprisingly natural for the size.
  Suitable for low-end hardware.

## Image Generation

- **[ComfyUI](https://github.com/comfyanonymous/ComfyUI)** — 🐧🪟🍎 🔓 🆓 🐍
  Node-graph workflow editor for diffusion models. Powers most modern
  local image and video pipelines.
- **[AUTOMATIC1111 / Stable Diffusion WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui)** — 🐧🪟🍎 🔓 🆓 🐍
  The original ergonomic SD UI. Heavy plugin ecosystem.
- **[Forge](https://github.com/lllyasviel/stable-diffusion-webui-forge)** — 🐧🪟🍎 🔓 🆓 🐍
  Performance-tuned A1111 fork by lllyasviel. Lower VRAM, faster on
  modern GPUs.
- **[Fooocus](https://github.com/lllyasviel/Fooocus)** — 🐧🪟🍎 🔓 🆓 🐍
  Image generator with sane defaults — minimal knobs for great
  results. Built on top of Stable Diffusion.
- **[InvokeAI](https://invoke.com)** — 🐧🪟🍎 🔓🔒 🆓💰 🐍
  Pro-grade SD UI with strong canvas / inpainting tools. Enterprise
  tier; free local install remains open source.
- **[SwarmUI](https://github.com/mcmonkeyprojects/SwarmUI)** — 🐧🪟🍎 🔓 🆓 🟦
  Modular UI built on top of ComfyUI. User-friendly mode out of the
  box, full node-graph available when you need it.
- **[SD.Next](https://github.com/vladmandic/sdnext)** — 🐧🪟🍎 🔓 🆓 🐍
  All-in-one fork of A1111 with broader backend support (Diffusers,
  ONNX, ROCm).

## Video Generation

- **[ComfyUI + LTX Video](https://github.com/comfyanonymous/ComfyUI)** — 🐧🪟🍎 🔓 🆓 🐍
  ComfyUI nodes drive Lightricks LTX video models for text-to-video
  and image-to-video generation. The chunked-loop pattern (released
  in our [comfyui-workflows](https://github.com/BrethofAI/comfyui-workflows))
  produces longer outputs than vanilla LTX allows.
- **[Wan2GP](https://github.com/deepbeepmeep/Wan2GP)** — 🐧🪟🍎 🔓 🆓 🐍
  Stripped-down Wan2.2 video pipeline for low-VRAM consumer GPUs.

## Code Assistants

- **[Aider](https://aider.chat)** — 🐧🪟🍎 🔓 🆓 🐍
  Terminal pair-programming. Bring-your-own-LLM via LiteLLM — run with
  Ollama or any OpenAI-compatible local endpoint.
- **[Continue](https://continue.dev)** — 🐧🪟🍎 🔓 🆓 🟦
  IDE assistant with first-class local-LLM support. Defaults can be
  set to Ollama / LM Studio. VS Code + JetBrains.
- **[Tabby](https://tabby.tabbyml.com)** — 🐧🪟🍎 🔓 🆓 🦀
  Self-hosted GitHub Copilot alternative. Local model serving with
  IDE plugins.
- **[Llama.vim](https://github.com/ggml-org/llama.vim)** — 🐧🪟🍎 🔓 🆓 ⚙️
  Vim plugin that streams llama.cpp completions inline. No cloud.
- **[twinny](https://github.com/twinnydotdev/twinny)** — 🐧🪟🍎 🔓 🆓 🟦
  Free local AI extension for VS Code. Chat + autocomplete via Ollama.

## Local Agents

- **[Open Interpreter](https://github.com/OpenInterpreter/open-interpreter)** — 🐧🪟🍎 🔓 🆓 🐍
  Code-execution agent that runs Python/shell on your machine.
  Local-LLM friendly.
- **[Continue Agent mode](https://docs.continue.dev/agent/how-to-use-it)** — 🐧🪟🍎 🔓 🆓 🟦
  Agentic editing flow inside Continue. Pair with a local model for
  fully-offline coding agents.
- **[Aider in /architect mode](https://aider.chat/docs/usage/modes.html)** — 🐧🪟🍎 🔓 🆓 🐍
  Aider's planning mode separates "decide" and "edit" steps; works
  well with strong local reasoning models.

## Vector Databases

- **[Chroma](https://www.trychroma.com)** — 🐧🪟🍎 🔓 🆓 🐍
  Embedding database designed for local-first usage. SQLite-style
  single-file or client/server.
- **[Qdrant](https://qdrant.tech)** — 🐧🪟🍎 🔓 🆓 🦀
  High-performance vector DB. Self-host the open-source binary.
- **[Weaviate](https://weaviate.io)** — 🐧🪟🍎 🔓 🆓 🐹
  Hybrid (vector + keyword) DB. Self-host the OSS distribution; cloud
  is optional.
- **[LanceDB](https://lancedb.com)** — 🐧🪟🍎 🔓 🆓 🦀
  Embedded, columnar vector DB. Single-file, no server.
- **[Marqo](https://www.marqo.ai)** — 🐧🪟🍎 🔓🔒 🆓💰 🐍
  End-to-end vector search; OSS core, paid hosted version.
- **[Faiss](https://github.com/facebookresearch/faiss)** — 🐧🪟🍎 🔓 🆓 ⚙️
  Library for similarity search. The retrieval engine inside many of
  the others.

## Embeddings

- **[Sentence Transformers](https://www.sbert.net)** — 🐧🪟🍎 🔓 🆓 🐍
  Reference Python library for sentence + paragraph embeddings.
- **[Nomic Embed](https://www.nomic.ai/blog/posts/nomic-embed-text-v1)** — 🐧🪟🍎 🔓 🆓 🐍
  Open-weights, fully reproducible long-context embedding model.
- **[BGE](https://github.com/FlagOpen/FlagEmbedding)** — 🐧🪟🍎 🔓 🆓 🐍
  BAAI's BGE family. Strong English + multilingual variants. Run via
  llama.cpp, sentence-transformers, or fastembed.
- **[fastembed](https://github.com/qdrant/fastembed)** — 🐧🪟🍎 🔓 🆓 🐍
  Lightweight CPU-friendly embedding library by Qdrant.

## Training & Fine-tuning

- **[Unsloth](https://unsloth.ai)** — 🐧🪟🍎 🔓 🆓 🐍
  Fine-tune LLMs 2× faster with 70% less VRAM than reference
  HuggingFace pipelines.
- **[Axolotl](https://github.com/axolotl-ai-cloud/axolotl)** — 🐧 🔓 🆓 🐍
  Config-driven fine-tuning framework. LoRA, QLoRA, full fine-tunes.
- **[MLX](https://github.com/ml-explore/mlx)** — 🍎 🔓 🆓 🐍
  Apple's native ML framework for Apple Silicon. Train and infer on
  M-series Macs without CUDA workarounds.
- **[Ostris ai-toolkit](https://github.com/ostris/ai-toolkit)** — 🐧🪟 🔓 🆓 🐍
  LoRA training UI for Flux, SD3, SDXL, LTX. Works on consumer
  hardware.
- **[diffusion-pipe](https://github.com/tdrussell/diffusion-pipe)** — 🐧 🔓 🆓 🐍
  Pipeline-parallel trainer for diffusion models. Multi-GPU LoRA on
  large image / video models.

## Local Search & RAG

- **[SearXNG](https://github.com/searxng/searxng)** — 🐧🪟🍎 🔓 🆓 🐍
  Self-hosted meta-search engine. Pair with a local LLM for an
  offline Perplexity-style assistant.
- **[Perplexica](https://github.com/ItzCrazyKns/Perplexica)** — 🐧🪟🍎 🔓 🆓 🟦
  Open-source AI search powered by SearXNG + your local LLM.
- **[PrivateGPT](https://github.com/zylon-ai/private-gpt)** — 🐧🪟🍎 🔓 🆓 🐍
  Ingest documents locally and query them with an offline LLM.
- **[LlamaIndex](https://www.llamaindex.ai)** — 🐧🪟🍎 🔓 🆓 🐍
  Toolkit for building RAG pipelines. Works fully offline with local
  models + vector DBs.
- **[Anything LLM](https://anythingllm.com)** — 🐧🪟🍎 🔓 🆓 🟦
  Self-hosted workspace tool with integrated RAG. Listed twice
  intentionally — strong both as a chat app and a RAG layer.

## Operating Systems Tuned for AI

- **[CachyOS](https://cachyos.org)** — 🐧 🔓 🆓
  Arch-based desktop distro with a tuned kernel and recent NVIDIA /
  AMD drivers. Sane out-of-the-box for new GPUs (Blackwell, RDNA 4).
- **[Bazzite](https://bazzite.gg)** — 🐧 🔓 🆓
  Container-native gaming and AI distro. Steam Deck-friendly, latest
  drivers, easy CUDA.
- **[Pop!_OS](https://pop.system76.com)** — 🐧 🔓 🆓
  System76's NVIDIA-friendly desktop distro. ISO ships with proprietary
  drivers for plug-and-play GPU work.
- **[NixOS](https://nixos.org)** — 🐧 🔓 🆓
  Reproducible system config. Best when you need identical CUDA + ML
  toolchain across machines.
- **[Bluefin](https://projectbluefin.io)** — 🐧 🔓 🆓
  Fedora-based, atomic, container-first. Good "drop you in a known
  state" workstation for AI work.

## Hardware-Specific Runtimes

- **[MLX](https://github.com/ml-explore/mlx)** — 🍎 🔓 🆓 🐍
  Apple Silicon-native ML library. Already listed under training; it
  also ships an inference runtime competitive with llama.cpp on M-series.
- **[ROCm + llama.cpp HIP](https://github.com/ggml-org/llama.cpp)** — 🐧🪟 🔓 🆓 ⚙️
  AMD GPU inference path. Llama.cpp's HIP backend now reaches CUDA
  parity on RDNA 3/4 in many workloads.
- **[OpenVINO](https://github.com/openvinotoolkit/openvino)** — 🐧🪟🍎 🔓 🆓 ⚙️
  Intel's inference toolkit. CPU, iGPU, dGPU (Arc), and NPU support
  for Intel laptops.
- **[NVIDIA TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM)** — 🐧🪟 🔒 🆓 🐍
  NVIDIA's optimised LLM runtime for their data-center and consumer
  GPUs. Closed-weights binary; fastest CUDA path for many models.

## Related work

- **[awesome-llms-txt](https://github.com/BrethofAI/awesome-llms-txt)** — Tools that publish `llms.txt` for agent discovery.
- **[awesome-private-ai](https://github.com/BrethofAI/awesome-private-ai)** — Privacy-first AI more broadly (some on this list, plus privacy-respecting cloud).
- **[awesome-mcp-servers](https://github.com/BrethofAI/awesome-mcp-servers)** — MCP servers, many of which sit happily next to a local LLM.
- **[awesome-ai-mine](https://github.com/BrethofAI/awesome-ai-mine)** — License + ToS analysis for the models you'll run locally.
- **[awesome-linux-for-ai](https://github.com/BrethofAI/awesome-linux-for-ai)** — Linux distros tuned for the AI workstations these tools live on.
- **[comfyui-workflows](https://github.com/BrethofAI/comfyui-workflows)** — Curated, working ComfyUI workflows for local image / video generation.
- **[anti-dev-tier-list](https://github.com/BrethofAI/anti-dev-tier-list)** — Anti-developer practices these local-AI tools route around.

## Contributing

Open an issue with the tool name, repo or homepage URL, the category
it should land in, and one paragraph on why it's worth listing. We do
not list tools whose offline mode is gated behind a paid plan.

## License

[MIT](LICENSE).

---

Maintained by **[Brethof AI](https://brethof.com)** — AI tools built for
people who take their data seriously.
