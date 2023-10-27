# DA CLIP URI for Windows

## Introduction

This is Windows model of DA CLIP URI.

original : [DA CLIP UIR](https://github.com/Algolzw/daclip-uir)

### Dependencies

- OS: Windows
- nvidia:
  - cuda: 11.7
- python 3.10.5 (using Pyenv)

## Install

## Clone from GitHub

Clone from GitHub, and move to the folder " daclip-uir-for-win ".

```bash
git clone https://github.com/supplepentan/daclip-uir-for-win
cd daclip-uir-for-win
```

## Virtual environment

Virtual environment with Python-version 3.10.5 using Pyenv.

```bash
pyenv local 3.10.5
python -m venv venv
venv/scripts/activate
```

## Libraries

Install libraries using " reqruirements.txt "

```bash
python -m pip install -r requirements.txt
```

### Pytorch

Uninstall unnecessary installed Pytorch, and newly install Pytorch (CUDA11.7 compatible model).

```bash
python -m pip uninstall -y torch torchvision
python -m pip install torch torchvision --index-url https://download.pytorch.org/whl/cu117
```

### Triton

Download " [triton-2.0.0-cp310-cp310-win_amd64.whl](https://huggingface.co/r4ziel/xformers_pre_built/resolve/main/triton-2.0.0-cp310-cp310-win_amd64.whl) " at root, and install.

```bash
python -m pip install triton-2.0.0-cp310-cp310-win_amd64.whl
```

## Pretrained Models

Download models " daclip_ViT-B-32.pt " and " universal-ir.pth " at folder " pretrained ".

| Model Name   | Description                                     | GoogleDrive                                                                                    | HuggingFace                                                                                      |
| ------------ | ----------------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| DA-CLIP      | Degradation-aware CLIP model                    | [download](https://drive.google.com/file/d/1A6u4CaVrcpcZckGUNzEXqMF8x_JXsZdX/view?usp=sharing) | [download](https://huggingface.co/weblzw/daclip-uir-ViT-B-32-irsde/blob/main/daclip_ViT-B-32.pt) |
| Universal-IR | DA-CLIP based universal image restoration model | [download](https://drive.google.com/file/d/1eXsyrmAbWOvhIY4Wbt5v4IxaggA5aZMG/view?usp=sharing) | [download](https://huggingface.co/weblzw/daclip-uir-ViT-B-32-irsde/blob/main/universal-ir.pth)   |

## Run

Move to the folder " universal-image-restoration/config/daclip-sde ", and run the gradio.

```bash
cd universal-image-restoration/config/daclip-sde
python app.py
```

Access to http://127.0.0.1:7860 .

## Acknowledgements

This code is built on [DA CLIP UIR](https://github.com/Algolzw/daclip-uir), thank for the authors for sharing their codes.
