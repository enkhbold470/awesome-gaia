# Awesome GAIA [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of awesome AMD GAIA projects, tools, tutorials, and resources.

[GAIA (Generative AI Is Awesome)](https://github.com/amd/gaia) is an open-source solution designed for the quick setup and execution of generative AI applications on local PC hardware. It enables fast and efficient execution of LLM-based applications using a hybrid hardware approach that combines the AMD Neural Processing Unit (NPU) and Integrated Graphics Processing Unit (iGPU) in Ryzen-AI PCs.

## Contents

- [Official Resources](#official-resources)
- [Community Projects](#community-projects)
- [Tutorials](#tutorials)
- [Articles](#articles)
- [Videos](#videos)
- [Models](#models)
- [Tools](#tools)
- [Applications](#applications)
- [Benchmarks](#benchmarks)
- [Discussions](#discussions)
- [In-depth Guides](#in-depth-guides)
- [Contributing](#contributing)

## Key Features

- 🏠 **Local LLM Processing**: Run powerful language models directly on your Windows device without cloud dependencies
- 🎯 **Multiple Use Cases**: From basic chat to RAG-enhanced applications and specialized agents
- ⚡ **Optimized Performance**: Leverages the AMD NPU and iGPU for hybrid acceleration
- 🖥️ **Easy-to-Use Interface**: Provides both CLI and GUI options
- 🔧 **Extensible Architecture**: Build and integrate your own agents and use cases
- 🔄 **Dual Mode**: 
  - **Hybrid Mode**: Optimized for Ryzen AI PCs (NPU + iGPU)
  - **Generic Mode**: Compatible with any Windows PC using Ollama backend

## Official Resources

- [AMD GAIA Repository](https://github.com/amd/gaia) - Official GitHub repository for GAIA.
- [AMD GAIA Documentation](https://github.com/amd/gaia/tree/main/docs) - Official documentation for GAIA.
- [GAIA CLI Documentation](https://github.com/amd/gaia/blob/main/docs/cli.md) - Guide to using the GAIA command-line interface.
- [AMD Developer Resources](https://www.amd.com/en/developer/resources/technical-articles/gaia-an-open-source-project-from-amd-for-running-local-llms-on-ryzen-ai.html) - Official AMD developer resources for GAIA.
- [GAIA Hardware Guide](https://github.com/amd/gaia/blob/main/docs/hardware.md) - Guide to hardware requirements and configurations for running GAIA.
- [GAIA Web UI Guide](https://github.com/amd/gaia/blob/main/docs/web.md) - Documentation for GAIA's web interface.
- [GAIA FAQ](https://github.com/amd/gaia/blob/main/docs/faq.md) - Frequently asked questions about GAIA.

## Community Projects

- *This section is for community-built projects that extend or enhance GAIA functionality. [Contribute](CONTRIBUTING.md) to add yours!*

## Tutorials

- [Getting Started with GAIA](https://github.com/amd/gaia/blob/main/docs/quickstart.md) - Official quickstart guide for setting up GAIA.
- [Running Mistral 7B on GAIA](https://github.com/amd/gaia/blob/main/docs/usage.md) - Guide to running Mistral 7B model using GAIA.
- [GAIA Installation Guide](https://github.com/amd/gaia/blob/main/docs/installation.md) - Detailed installation instructions for GAIA.
- [Our Getting Started Guide](getting-started.md) - Our comprehensive guide to setting up and using GAIA.

## Articles

- [AMD Announces Open-Source "GAIA" For GenAI](https://www.phoronix.com/news/AMD-GAIA-Open-Source) - Introduction to the GAIA project on Phoronix.
- [AMD launches Gaia open source project for running LLMs locally on any PC](https://www.tomshardware.com/tech-industry/artificial-intelligence/amd-launches-gaia-open-source-project-for-running-llms-locally-on-any-pc) - Overview of GAIA on Tom's Hardware.
- [AMD's GAIA Project Lets You Run LLMs Locally](https://www.techpowerup.com/323546/amds-gaia-project-lets-you-run-llms-locally) - TechPowerUp article discussing GAIA's capability to run LLMs locally.
- [AMD Takes On Qualcomm With NPU, GPU-Accelerated Gaia LLM Platform](https://www.crn.com/news/amd-takes-on-qualcomm-with-npu-gpu-accelerated-gaia-llm-platform) - CRN article comparing AMD's GAIA with Qualcomm's solutions.
- [AMD GAIA Project Is Now Open Source](https://www.linuxfordevices.com/news/amd-gaia-project-opensource) - Linux For Devices coverage of GAIA becoming open source.

## Videos

- *This section is for videos about GAIA. [Contribute](CONTRIBUTING.md) to add yours!*

## Models

### Currently Supported Models

#### Hybrid Mode (NPU+iGPU)

| LLM | Checkpoint | Data Type |
|-----|------------|-----------|
| Phi-3.5 Mini Instruct | amd/Phi-3.5-mini-instruct-awq-g128-int4-asym-fp16-onnx-hybrid | int4 |
| Phi-3 Mini Instruct | amd/Phi-3-mini-4k-instruct-awq-g128-int4-asym-fp16-onnx-hybrid | int4 |
| Llama-2 7B Chat | amd/Llama-2-7b-chat-hf-awq-g128-int4-asym-fp16-onnx-hybrid | int4 |
| Llama-3.2 1B Instruct | amd/Llama-3.2-1B-Instruct-awq-g128-int4-asym-fp16-onnx-hybrid | int4 |
| Llama-3.2 3B Instruct | amd/Llama-3.2-3B-Instruct-awq-g128-int4-asym-fp16-onnx-hybrid | int4 |
| Qwen 1.5 7B Chat | amd/Qwen1.5-7B-Chat-awq-g128-int4-asym-fp16-onnx-hybrid | int4 |
| Mistral 7B Instruct | amd/Mistral-7B-Instruct-v0.3-awq-g128-int4-asym-fp16-onnx-hybrid | int4 |

#### Generic Mode (CPU/GPU with Ollama)

| LLM | Checkpoint | Device | Data Type |
|-----|------------|--------|-----------|
| Llama 3.2 1B | llama3.2:1b | CPU/GPU | Q8_0 |
| Llama 3.2 3B | llama3.2:3b | CPU/GPU | Q4_K_M |
| Llama 3.1 8B | llama3.2:8b | CPU/GPU | Q4_0 |

### Other Compatible Models

- [Mistral 7B](https://huggingface.co/mistralai/Mistral-7B-v0.1) - 7B parameter model officially supported by GAIA.
- [Phi-2](https://huggingface.co/microsoft/phi-2) - 2.7B parameter model compatible with GAIA.
- [Llama 2](https://huggingface.co/meta-llama/Llama-2-7b) - Meta's 7B parameter model that can be run with GAIA.
- [Vicuna 7B](https://huggingface.co/lmsys/vicuna-7b-v1.5) - Fine-tuned LLaMA model that works with GAIA.
- [See detailed model comparison](model-comparison.md) - Comprehensive comparison of models compatible with GAIA.

## Tools

- [GAIA Command Line Interface](https://github.com/amd/gaia/blob/main/docs/cli.md) - Official CLI tool for interacting with GAIA.
- [GAIA Web Interface](https://github.com/amd/gaia/blob/main/docs/web.md) - Web-based UI for interacting with GAIA models.

## Applications

GAIA currently supports the following use cases:

| Use Case | Function | Description |
|----------|----------|-------------|
| No Agent | Basic completion | Direct model interaction for testing |
| Chaty | Basic LLM chatbot | Conversational interface with history |
| Joker | Simple RAG joke generator | Demonstrates retrieval-augmented generation |
| Clip | YouTube search and Q&A | Video transcript Q&A (requires YouTube API key) |

## Benchmarks

- [GAIA Performance Guide](https://github.com/amd/gaia/blob/main/docs/performance.md) - Performance insights and optimization tips for GAIA.

## Discussions

- [Reddit r/LocalLLaMA - GAIA Discussion](https://www.reddit.com/r/LocalLLaMA/comments/1cxh4n3/amd_gaia_project_for_running_llms_in_windows/) - Community discussion about GAIA on Reddit.
- [HackerNews - AMD GAIA](https://news.ycombinator.com/item?id=39885233) - HackerNews thread discussing the AMD GAIA project.

## In-depth Guides

This repository includes several comprehensive guides to help you get the most out of GAIA:

### [Getting Started Guide](getting-started.md)

A detailed walkthrough for setting up and using GAIA, including:
- Installation steps
- First steps with GAIA
- Working with models
- Advanced configuration
- Troubleshooting

### [Hardware Requirements Guide](hardware-guide.md)

Everything you need to know about hardware for GAIA:
- Minimum requirements
- Recommended hardware
- Supported devices
- Performance expectations
- Troubleshooting hardware issues

### [Model Comparison Guide](model-comparison.md)

Detailed comparison of models that work with GAIA:
- Small models (< 3B parameters)
- Medium models (3-10B parameters)
- Fine-tuned variants
- Performance benchmarks
- Model selection guidelines

### [GAIA vs Alternatives](gaia-vs-alternatives.md)

How GAIA compares to other local LLM solutions:
- Comparison with Ollama, LM Studio, llama.cpp, and Text Generation WebUI
- Feature comparison
- Performance analysis
- Use case recommendations
- Community and support

## System Requirements

GAIA with Ryzen AI Hybrid NPU/iGPU execution requires:

- Systems: Asus ProArt PX13/P16, HP Omnibook or similar with Ryzen AI 9 HX 370 or higher
- OS: Windows 11 Pro/Home
- Processor: AMD Ryzen AI 9 HX 370 w/ Radeon 890M
- AMD Radeon 890M iGPU drivers: `32.0.12010.8007` and `32.0.12033.1030`
- AMD NPU drivers: `32.0.203.237` or `32.0.203.240`
- Physical Memory: Minimum 16GB, Recommended 32GB

For Generic mode, GAIA can run on any Windows PC meeting Ollama's system requirements.

## Contributing

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0)

To the extent possible under law, the contributors have waived all copyright and related or neighboring rights to this work.