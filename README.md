# text-to-image-generation

# Text-to-Image Generation Using Stable Diffusion XL

## Project Overview

This project generates images from text prompts using Stable Diffusion XL (SDXL) and the Hugging Face Diffusers library in Google Colab.

## Features

* Text-to-image generation
* Stable Diffusion XL model
* GPU acceleration with Google Colab
* Customizable prompts
* High-quality image output

## Technologies Used

* Python
* PyTorch
* Hugging Face Diffusers
* Stable Diffusion XL
* Google Colab

## Installation

Open the notebook in Google Colab and run:

```python
!pip install -q diffusers transformers accelerate torch safetensors
```

## Usage

1. Open the notebook in Google Colab.
2. Enable GPU:

   * Runtime → Change runtime type → T4 GPU
3. Run all notebook cells.
4. Enter a text prompt.
5. Generated images will be displayed and can be saved.

## Example Prompt

A futuristic city at sunset, ultra detailed, cinematic lighting, 8k, masterpiece

## Model

stabilityai/stable-diffusion-xl-base-1.0

## Output

The generated image is saved as:

generated.png

## Future Enhancements

* Gradio web interface
* Image-to-image generation
* Multiple style presets
* Batch image generation
