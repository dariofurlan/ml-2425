
# DNABERT Installation Guide

This guide will help you set up DNABERT (DNA Bidirectional Encoder Representations from Transformers) on your system.

## Development Environment

The following environment was used for developing and testing this guide:

- **OS**: Debian 12.8 (bookworm)
- **Conda**: 25.3.1
- **Rust**: 1.87.0 (17067e9ac 2025-05-09)
- **CUDA**: 12.4 (550.54.14)

## Prerequisites

Before proceeding with the installation, make sure you have:

- **Miniconda** or Anaconda installed and added to your PATH
- **Rust** installed and added to your PATH

You can verify their installation with these commands:
```bash
conda --version
rustc --version
```

## Installation Steps

### 1. Install PyTorch

First, install PyTorch with CUDA support:

```bash
conda install pytorch torchvision -c pytorch
```

### 2. Clone the DNABERT Repository

```bash
git clone https://github.com/jerryji1993/DNABERT
cd DNABERT
```

### 3. Install DNABERT and Dependencies

Install sentencepiece (note the correct version):

```bash
python3 -m pip install sentencepiece==0.2.0
```

Install DNABERT in development mode:

```bash
python3 -m pip install --editable .
```

Install example-specific requirements:

```bash
cd examples
python3 -m pip install -r requirements.txt
```

Download the pre-trained model of K-mer (e.g. 6-mer) onto the examples directory, the model will be saved in `examples/ft/6`:
```bash
mkdir ft
cd ft
git clone https://huggingface.co/zhihan1996/DNA_bert_6 6
```

## Verification

You can verify your installation by running one of the example scripts or notebooks in the examples directory.

## Troubleshooting

If you encounter any issues during installation:
- Make sure your CUDA drivers are compatible with the installed PyTorch version
- Check that all prerequisites are correctly installed and available in your PATH
- For dependency conflicts, consider creating a new conda environment

