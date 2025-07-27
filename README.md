---
license: apache-2.0
language:
- en
base_model:
- HuggingFaceTB/SmolLM2-135M-Instruct
pipeline_tag: text-generation
tags:
- gguf
- q8_0
- quantized
- llama
- llama.cpp
- smollm2
- embedded-ai
- lightweight
- fast-inference
- efficient
- tiny-llm
---
# SmolLM2 135M Instruct (Quantized Q8_0, GGUF)

A tiny yet powerful instruction-tuned language model optimized for CPU inference. With only 135 million parameters and a file size of 138 MB, this model delivers impressive performance even on modest hardware.

## 🌟 Key Features

- **Tiny Footprint**: Only 138 MB in size
- **CPU-Friendly**: Runs efficiently without a GPU
- **Low Resource Requirements**: Works on systems with just 1-2 GB RAM
- **Fast Inference**: Responsive even on older CPUs 
- **Instruction-Tuned**: Optimized for chat and instruction-following tasks
- **Long Context**: Supports up to 8,192 tokens

## 📦 Model Details

- **Architecture**: LLaMA-like transformer
- **Parameters**: 135M
- **Format**: GGUF (compatible with llama.cpp ecosystem)
- **Quantization**: Q8_0 (8-bit linear quantization)
- **Type**: Instruction-tuned chat model

## 🗂️ Repository Contents

- `smollm2-135m-instruct-q8_0.gguf` - Main model file (Q8_0 quantized)
- `tokenizer.json` - Model tokenizer file
- `config.json` - HuggingFace compatibility configuration
- `LICENSE` - Apache 2.0 license file
- `README.md` - This documentation

## 🚀 Quick Start Guide

### Prerequisites
```bash
# Install llama-cpp-python
pip install llama-cpp-python
```

### Using llama.cpp CLI

```bash
# Basic usage
./main -m smollm2-135m-instruct-q8_0.gguf -p "Who are you?"

# With custom parameters
./main -m smollm2-135m-instruct-q8_0.gguf --ctx-size 2048 --threads 4 -p "Write a story."
```

### Using Python with llama-cpp-python

```python
from llama_cpp import Llama

# Initialize the model
llm = Llama(
    model_path="smollm2-135m-instruct-q8_0.gguf",
    n_ctx=2048,           # Context window
    n_threads=4,          # CPU threads to use
    n_batch=512          # Batch size for prompt processing
)

# Generate a response
output = llm("What is the capital of France?", 
            max_tokens=128,
            temperature=0.7,
            top_p=0.95)
print(output)
```

## 💬 Prompt Format

This is a chat-style instruction-tuned model. Use the following message format for best results:

```json
[
  {"role": "system", "content": "You are a helpful AI assistant."},
  {"role": "user", "content": "Tell me a joke."}
]
```

### Example Interaction

```
User: What is your name?

Luna: My name is Luna, and I'm your tiny but capable AI assistant, ready to help with anything you need!
```

## 🔧 Compatible Software

- llama.cpp
- text-generation-webui
- LM Studio
- KoboldCPP
- llama-cpp-python

## 💪 Why Choose This Model?

- ✨ **Runs Offline**: No internet connection needed
- 📱 **Tiny Footprint**: Just 138 MB on disk
- ⚡ **Fast Inference**: Optimized for CPU performance
- 🌐 **Open Source**: Apache 2.0 licensed
- 🛠️ **Versatile**: Perfect for edge devices, embedded systems, hobby projects, and learning

## 🥲 Limitations

SmolLM2 models primarily understand and generate content in English. They can produce text on a variety of topics, but the generated content may not always be factually accurate, logically consistent, or free from biases present in the training data. These models should be used as assistive tools rather than definitive sources of information. Users should always verify important information and critically evaluate any generated content.


## 📄 License

[Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0) 

## 🙏 Credits

- Quantized and packaged by Ayush Swami (HackNetAyush)
- Based on HuggingFaceTB's SmolLM2-135M-Instruct model

## 💻 Hardware Requirements

- CPU: Any modern CPU
- RAM: 1-2 GB minimum
- GPU: Not required
- Disk Space: ~140 MB

Feel free to Like ❤️ the repository if you find this model useful!