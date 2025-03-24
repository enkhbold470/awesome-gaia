# GAIA Model Comparison Guide

This guide compares various language models that are compatible with AMD GAIA, highlighting their performance, capabilities, and use cases.

## Overview of Compatible Models

GAIA can run various open-source language models, with performance depending on the model size, quantization, and hardware configuration. Here's a comparison of popular models that work well with GAIA:

## Small Models (< 3B parameters)

### Phi-2 (2.7B)
- **Size**: 2.7 billion parameters
- **Developer**: Microsoft
- **License**: MIT
- **Quantization Options**: 4-bit, 8-bit
- **Performance on GAIA**: Very Fast (20-25 tokens/sec with NPU+GPU)
- **Use Cases**: Code completion, lightweight assistants, text generation
- **Strengths**: Excellent performance for its size, good coding abilities
- **Limitations**: Less contextual understanding than larger models
- **Download**: [Hugging Face](https://huggingface.co/microsoft/phi-2)

### TinyLlama (1.1B)
- **Size**: 1.1 billion parameters
- **Developer**: DAMO Academy
- **License**: Apache 2.0
- **Quantization Options**: 4-bit, 8-bit
- **Performance on GAIA**: Extremely Fast (30+ tokens/sec with NPU+GPU)
- **Use Cases**: Quick responses, simple assistants, resource-constrained environments
- **Strengths**: Very small size, high speed
- **Limitations**: Limited reasoning abilities
- **Download**: [Hugging Face](https://huggingface.co/TinyLlama/TinyLlama-1.1B-Chat-v1.0)

## Medium Models (3-10B parameters)

### Mistral 7B
- **Size**: 7 billion parameters
- **Developer**: Mistral AI
- **License**: Apache 2.0
- **Quantization Options**: 4-bit, 5-bit, 8-bit
- **Performance on GAIA**: Good (10-15 tokens/sec with NPU+GPU)
- **Use Cases**: General purpose assistant, content generation, summarization
- **Strengths**: Strong reasoning abilities, efficient architecture
- **Limitations**: Moderate resource requirements
- **Download**: [Hugging Face](https://huggingface.co/mistralai/Mistral-7B-v0.1)

### Llama 2 7B
- **Size**: 7 billion parameters
- **Developer**: Meta
- **License**: Llama 2 Community License
- **Quantization Options**: 4-bit, 8-bit
- **Performance on GAIA**: Good (8-14 tokens/sec with NPU+GPU)
- **Use Cases**: General assistant, creative writing, chat
- **Strengths**: Well-rounded capabilities, good instruction following
- **Limitations**: Requires verification for commercial use
- **Download**: [Hugging Face](https://huggingface.co/meta-llama/Llama-2-7b)

### Neural Chat 7B
- **Size**: 7 billion parameters
- **Developer**: Intel
- **License**: Intel Neural Chat License
- **Quantization Options**: 4-bit, 8-bit
- **Performance on GAIA**: Good (8-12 tokens/sec with NPU+GPU)
- **Use Cases**: Chat assistants, customer service, instruction following
- **Strengths**: Well-optimized for conversation, good instruction following
- **Limitations**: Less versatile than some other models
- **Download**: [Hugging Face](https://huggingface.co/Intel/neural-chat-7b-v3-1)

## Fine-tuned Variants

### Mixtral 8x7B (MoE)
- **Size**: 8x7 billion parameters (Mixture of Experts architecture)
- **Developer**: Mistral AI
- **License**: Apache 2.0
- **Quantization Options**: 4-bit, 8-bit
- **Performance on GAIA**: Moderate (5-8 tokens/sec with GPU-only mode)
- **Use Cases**: Advanced reasoning, complex tasks
- **Strengths**: Near-Llama 70B performance in much smaller package
- **Limitations**: Only works in GPU-only mode, requires more resources
- **Download**: [Hugging Face](https://huggingface.co/mistralai/Mixtral-8x7B-v0.1)

### Vicuna 7B
- **Size**: 7 billion parameters
- **Developer**: LMSYS
- **License**: Non-commercial research
- **Quantization Options**: 4-bit, 8-bit
- **Performance on GAIA**: Good (8-15 tokens/sec with NPU+GPU)
- **Use Cases**: Research, conversation, general assistant
- **Strengths**: Good conversation abilities, well-fine-tuned
- **Limitations**: Non-commercial license restrictions
- **Download**: [Hugging Face](https://huggingface.co/lmsys/vicuna-7b-v1.5)

## Model Selection Guidelines

When choosing a model to use with GAIA, consider:

1. **Hardware Constraints**: 
   - For NPU+GPU mode: Prefer models 7B or smaller
   - For GPU-only mode: Can run larger models but with slower performance

2. **Task Requirements**:
   - Simple responses: Smaller models like Phi-2 are sufficient
   - Complex reasoning: Mistral 7B or larger recommended
   - Code generation: Phi-2 or CodeLlama variants
   - Conversations: Vicuna or Neural Chat models

3. **License Considerations**:
   - Commercial use: Check license restrictions (especially for Llama models)
   - Open models: Mistral and some Phi models have permissive licenses

4. **Quantization**:
   - 4-bit: Faster, uses less memory, slight quality reduction
   - 8-bit: Better quality, requires more memory, slower

## Performance Benchmarks

Below are approximate inference speeds for models running on a Ryzen AI 9 8945HS system with 32GB RAM:

| Model | Parameters | Quantization | NPU+GPU Mode | GPU-Only Mode |
|-------|------------|--------------|--------------|---------------|
| Phi-2 | 2.7B | 4-bit | 25 tokens/sec | 15 tokens/sec |
| TinyLlama | 1.1B | 4-bit | 35 tokens/sec | 20 tokens/sec |
| Mistral | 7B | 4-bit | 15 tokens/sec | 8 tokens/sec |
| Llama 2 | 7B | 4-bit | 14 tokens/sec | 7 tokens/sec |
| Vicuna | 7B | 4-bit | 13 tokens/sec | 7 tokens/sec |
| Mixtral 8x7B | 46B effective | 4-bit | Not supported | 5 tokens/sec |

*Note: These are approximate values and actual performance may vary based on specific hardware configurations, prompt length, and other factors.*

## Tips for Optimizing Model Performance

1. **Try different quantization levels** to find the balance between speed and quality
2. **Adjust context length** based on your needs (shorter contexts process faster)
3. **Set appropriate temperature values** for your use case
4. **Consider using different models** for different tasks
5. **Update to the latest GAIA version** for performance improvements and optimizations