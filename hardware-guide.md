# GAIA Hardware Requirements Guide

This guide provides information about the hardware requirements and recommendations for running AMD GAIA efficiently.

## Minimum Requirements

GAIA is designed to run on Ryzen AI PCs with NPU (Neural Processing Unit) capabilities. Here are the minimum requirements:

- **Processor**: AMD Ryzen AI 8040 series or newer
- **RAM**: 16GB (32GB recommended for larger models)
- **Storage**: 20GB free space for GAIA installation and basic models
- **Operating System**: Windows 11 (Linux support is planned)
- **GPU**: Integrated AMD Radeon Graphics supporting DirectML
- **NPU**: AMD XDNA NPU with minimum 16 TOPS

## Recommended Hardware

For optimal performance with GAIA, especially when running larger models:

- **Processor**: AMD Ryzen AI 9 8945HS or newer
- **RAM**: 32GB or more
- **Storage**: 100GB+ SSD for multiple models
- **GPU**: AMD Radeon 780M iGPU or better

## Hardware Modes

GAIA operates in two primary modes:

### 1. NPU + GPU Mode (Hybrid Mode)
- Uses both NPU and integrated GPU for optimal performance
- Best for 7B parameter models
- Provides the fastest inference times for supported models

### 2. GPU-Only Mode
- Uses only the integrated GPU
- Compatible with wider range of models
- Allows running larger models that don't fit on the NPU

## Supported Devices

GAIA has been tested and confirmed to work well on the following devices:

- Lenovo Yoga Slim 7x (Ryzen AI 9 8945HS)
- ASUS Zenbook S 14 (Ryzen AI 9 8940HS)
- HP EliteBook (Ryzen AI 7 8840HS)
- Acer Swift Edge 16 (Ryzen AI 9 8945HS)

## Performance Expectations

Performance varies depending on the hardware configuration and model size:

| Model | Parameters | NPU+GPU Mode | GPU-Only Mode |
|-------|------------|--------------|---------------|
| Phi-2 | 2.7B | 25 tokens/sec | 15 tokens/sec |
| Mistral | 7B | 15 tokens/sec | 8 tokens/sec |
| Llama 2 | 7B | 14 tokens/sec | 7 tokens/sec |

*Note: These are approximate values and actual performance may vary based on specific hardware configurations.*

## Troubleshooting Hardware Issues

If you encounter hardware-related issues while running GAIA:

1. **NPU Not Detected**: 
   - Ensure you have the latest AMD drivers installed
   - Verify NPU is enabled in BIOS settings
   - Check Windows Device Manager for any driver issues

2. **Performance Issues**:
   - Close other GPU-intensive applications
   - Reduce model quantization (try 4-bit instead of 8-bit)
   - Set Windows power plan to "High Performance"

3. **Out of Memory Errors**:
   - Try smaller models or different quantization
   - Close unnecessary applications
   - Use GPU-only mode for certain models

## Future Hardware Support

AMD has announced plans to expand GAIA support to:
- More Ryzen AI devices
- Select discrete AMD GPUs
- Linux operating systems

Stay tuned to the [official GAIA repository](https://github.com/amd/gaia) for updates on hardware support.