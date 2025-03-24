# Getting Started with GAIA

This guide will walk you through the process of setting up and using AMD GAIA for running local language models on your Ryzen AI PC.

## Prerequisites

Before you begin, ensure your system meets the following requirements:
- Windows 11 operating system
- AMD Ryzen AI processor (8040 series or later) with NPU
- Minimum 16GB RAM (32GB recommended)
- At least 20GB free storage space

## Installation Steps

### 1. Install GAIA

#### Using the Installer

1. Download the latest GAIA installer from the [releases page](https://github.com/amd/gaia/releases)
2. Run the installer and follow the on-screen instructions
3. When prompted, select the installation directory (default is recommended)
4. Complete the installation process

#### Using Python (Advanced)

For developers who prefer to install from source:

```bash
# Clone the repository
git clone https://github.com/amd/gaia.git
cd gaia

# Create and activate a virtual environment
python -m venv venv
.\venv\Scripts\activate

# Install dependencies
pip install -e .
```

### 2. Launch GAIA

After installation, you can launch GAIA in several ways:

#### Using the Windows Start Menu

1. Open the Windows Start Menu
2. Search for "GAIA"
3. Click on the GAIA application icon

#### Using the Command Line

Open a command prompt and run:

```bash
gaia
```

This will start GAIA with the default settings.

## First Steps with GAIA

### 1. Using the Web UI

Upon launching GAIA, a web interface will open in your default browser (typically at http://localhost:8080).

From the web interface, you can:
- Browse and download available models
- Chat with installed models
- Adjust model settings
- Monitor performance

### 2. Using the Command Line

GAIA also provides a powerful command-line interface for advanced users:

```bash
# List available models
gaia models list

# Download a model
gaia models download mistral-7b

# Start a chat session with a specific model
gaia chat --model mistral-7b

# Run in GPU-only mode
gaia chat --model mistral-7b --mode gpu-only

# Start the web UI on a specific port
gaia web --port 8888
```

## Working with Models

### Downloading Models

1. In the web UI, go to the "Models" tab
2. Browse the available models or search for a specific one
3. Click "Download" next to the model you want to use
4. Wait for the download and initialization to complete

### Chat Interface

1. Go to the "Chat" tab in the web UI
2. Select a model from the dropdown menu
3. Type your message in the input box and press Enter or click Send
4. The model will process your input and generate a response

### Adjusting Settings

To optimize the model's performance or output:

1. Click on the "Settings" icon in the chat interface
2. Adjust parameters such as:
   - Temperature (higher values = more creative, lower = more focused)
   - Top P (controls randomness of token selection)
   - Context length (how much previous conversation to include)
   - Execution mode (NPU+GPU or GPU-only)
3. Save your settings to apply them

## Advanced Configuration

### Custom Prompt Templates

GAIA supports custom prompt templates to format conversations for different models:

1. Navigate to the GAIA installation directory
2. Open the `config` folder
3. Edit or create a template file (see examples in the folder)
4. Restart GAIA to apply the changes

### Using Different Quantization Levels

To balance performance and quality:

```bash
# Run a model with 4-bit quantization
gaia chat --model mistral-7b --quantization q4_0

# Run a model with 8-bit quantization (higher quality, slower)
gaia chat --model mistral-7b --quantization q8_0
```

## Troubleshooting Common Issues

### Model Download Failures

If you encounter issues downloading models:

1. Check your internet connection
2. Ensure you have enough disk space
3. Try downloading with the command line using:
   ```bash
   gaia models download <model-name> --force
   ```

### Performance Issues

If the model is running slowly:

1. Try a smaller model (e.g., Phi-2 instead of Mistral 7B)
2. Use 4-bit quantization instead of 8-bit
3. Reduce the context length
4. Close other resource-intensive applications
5. Ensure your system is set to "High Performance" power plan

### NPU Not Detected

If GAIA cannot detect your NPU:

1. Verify your processor has a compatible NPU
2. Check for AMD driver updates
3. Ensure NPU is enabled in BIOS settings
4. Run GAIA with the `--mode gpu-only` flag as a fallback

## Further Resources

- [Official GAIA Documentation](https://github.com/amd/gaia/tree/main/docs)
- [GAIA CLI Reference](https://github.com/amd/gaia/blob/main/docs/cli.md)
- [Hardware Guide](hardware-guide.md)
- [Model Comparison Guide](model-comparison.md)
- [GAIA GitHub Repository](https://github.com/amd/gaia)

## Community Support

If you need help with GAIA:

- [GitHub Issues](https://github.com/amd/gaia/issues) - Report bugs or request features
- [Reddit r/LocalLLaMA](https://www.reddit.com/r/LocalLLaMA/) - Community discussions
- [AMD Developer Forums](https://community.amd.com/)