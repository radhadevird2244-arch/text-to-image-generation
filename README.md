# AI Text-to-Image Generator using Stable Diffusion XL Turbo

##  Project Overview

This project is a **Text-to-Image Generator** built using **Stable Diffusion XL Turbo (SDXL Turbo)** from Hugging Face's **Diffusers** library.

The application takes a text prompt as input and generates a high-quality AI image in just a few seconds using a GPU on **Google Colab**.

This project demonstrates the practical use of **Generative AI**, **Diffusion Models**, and **PyTorch** for image synthesis.

---

# Features

* Generate images from natural language prompts
* Uses Stable Diffusion XL Turbo
* Fast image generation (2–5 seconds on Google Colab GPU)
* High-quality AI-generated images
* Automatically saves the generated image
* Optimized for Google Colab
* Beginner-friendly implementation

---

# Technologies Used

| Technology                | Purpose                   |
| ------------------------- | ------------------------- |
| Python                    | Programming Language      |
| Google Colab              | Development Environment   |
| PyTorch                   | Deep Learning Framework   |
| Hugging Face Diffusers    | Stable Diffusion Pipeline |
| Transformers              | Model Support             |
| Accelerate                | Faster GPU Execution      |
| Safetensors               | Secure Model Loading      |
| xFormers                  | Memory Optimization       |
| Stable Diffusion XL Turbo | AI Image Generation Model |

---

# Libraries Used

```python
torch
diffusers
transformers
accelerate
safetensors
xformers
time
IPython.display
```

---

# Model Used

**Model Name**

Stable Diffusion XL Turbo

```
stabilityai/sdxl-turbo
```

This model is designed for extremely fast image generation while maintaining excellent image quality.

---

# Project Workflow

```
Start

↓

Install Required Libraries

↓

Import Libraries

↓

Detect GPU

↓

Load SDXL Turbo Model

↓

Enable Optimizations

↓

Enter Text Prompt

↓

Generate AI Image

↓

Save Image

↓

Display Image

↓

End
```

---

# Project Structure

```
AI-Text-to-Image-Generator/

│

├── Text_To_Image_Generator.ipynb

├── generated_image.png

├── README.md

└── requirements.txt
```

---

# Installation

Clone the repository

```bash
git clone https://github.com/yourusername/AI-Text-to-Image-Generator.git
```

Move into the project directory

```bash
cd AI-Text-to-Image-Generator
```

Install the required libraries

```bash
pip install diffusers transformers accelerate safetensors xformers torch
```

---

# Running in Google Colab

Open Google Colab.

Enable GPU:

```
Runtime

↓

Change Runtime Type

↓

Hardware Accelerator

↓

GPU

↓

Save
```

Run the notebook cells one by one.

---

# Execution Process

## Step 1

Install the required libraries.

```python
!pip install diffusers transformers accelerate safetensors xformers
```

---

## Step 2

Import all required libraries.

```python
import torch
import time
from diffusers import AutoPipelineForText2Image
from IPython.display import display
```

---

## Step 3

Check whether GPU is available.

```python
device = "cuda" if torch.cuda.is_available() else "cpu"
```

---

## Step 4

Load the Stable Diffusion XL Turbo model.

```python
pipe = AutoPipelineForText2Image.from_pretrained(
    "stabilityai/sdxl-turbo",
    torch_dtype=torch.float16,
    variant="fp16"
)
```

---

## Step 5

Move the model to GPU.

```python
pipe = pipe.to(device)
```

---

## Step 6

Enable memory optimization.

```python
pipe.enable_attention_slicing()

pipe.enable_vae_slicing()
```

---

## Step 7

Accept a prompt from the user.

Example:

```
A futuristic city at sunset with flying cars
```

---

## Step 8

Generate the image.

```python
image = pipe(
    prompt,
    num_inference_steps=4,
    guidance_scale=0.0,
    height=1024,
    width=1024
).images[0]
```

---

## Step 9

Save the generated image.

```python
image.save("generated_image.png")
```

---

## Step 10

Display the generated image.

```python
display(image)
```

---

# Methods Used

## 1. Diffusion Models

The project uses diffusion-based generative models to convert random noise into realistic images.

---

## 2. Stable Diffusion XL Turbo

An optimized version of Stable Diffusion XL capable of generating images in only a few inference steps.

---

## 3. GPU Acceleration

PyTorch automatically uses CUDA to speed up inference.

---

## 4. Memory Optimization

The following optimizations are enabled:

* Attention Slicing
* VAE Slicing
* FP16 (Half Precision)

These reduce GPU memory usage while improving generation speed.

---

# Parameters Used

| Parameter      | Value      |
| -------------- | ---------- |
| Model          | SDXL Turbo |
| Height         | 1024       |
| Width          | 1024       |
| Steps          | 4          |
| Guidance Scale | 0.0        |
| Precision      | FP16       |

---

# Sample Prompt

```
A majestic white tiger walking through a snowy forest during sunrise, ultra realistic, cinematic lighting, 8K
```

---

# Sample Output

```
generated_image.png
```

The generated image is automatically saved in the current working directory.

---

# Advantages

* Very fast image generation
* High-quality outputs
* Easy to use
* Beginner friendly
* Open-source model
* GPU accelerated
* Suitable for portfolio projects

---

# Future Enhancements

* Negative prompt support
* Image style selection
* Multiple image generation
* Custom image resolution
* Random seed control
* Web interface using Streamlit
* Gradio application
* Image-to-image generation
* Prompt history
* Download button

---

# Applications

* AI Art
* Digital Painting
* Game Asset Generation
* Character Design
* Product Concept Design
* Graphic Design
* Advertising
* Story Illustration
* Educational Content
* Creative Media

---

# Author

**Nagesh Jakkavarapu**

Built as a Generative AI portfolio project using Stable Diffusion XL Turbo and Hugging Face Diffusers.

---

# License

This project is intended for educational and portfolio purposes.
