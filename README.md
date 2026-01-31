## Overview

The application uses the Evo2 biological large language model to predict whether single nucleotide variants (SNVs) in human DNA are pathogenic or benign. The goal of this project was to explore the intersection of AI, genomics, and scalable ML deployment, while building a production-style system end-to-end.

The project includes:

A GPU-accelerated Python backend deployed on Modal (H100 serverless GPU)

A FastAPI inference service for variant analysis

A modern, responsive web application for genome and gene exploration

TL;DR / Simpler Version\
DNA is like a long code made of A, T, G, and C. Small changes (mutations) in specific parts of this code, like in genes responsible for preventing cancer, can increase a person's risk of developing the disease. For instance, if an 'A' appears where a 'T' should be at a particular spot, that's a mutation. These changes can vary in how harmful they are, and we'll build a tool to analyze these different variations' harmfulness.

Features:

- 🧬 Evo2 model for variant effect prediction
- 🩺 Predict pathogenicity of single nucleotide variants (pathogenic/benign)
- ⚖️ Comparison view for existing ClinVar classification vs. Evo2 prediction
- 💯 Prediction confidence estimation
- 🌍 Genome assembly selector (e.g., hg38)
- 🗺️ Select genes from chromosome browsing or searching (e.g., BRCA1)
- 🌐 See full reference genome sequence (UCSC API)
- 🧬 Explore gene and variants data (NCBI ClinVar/E-utilities)
- 💻 Python backend deployed with Modal
- 🚀 FastAPI endpoint for variant analysis requests
- ⚡ GPU-accelerated (H100) variant scoring via Modal
- 📱 Responsive Next.js web interface
- 🎨 Modern UI with Tailwind CSS & Shadcn UI

## Evo2 Model

Check out the paper behind the model.

- [Paper](https://www.biorxiv.org/content/10.1101/2025.02.18.638918v1)
- [GitHub Repository](https://github.com/ArcInstitute/evo2)

## Setup

Follow these steps to install and set up the project.

### Clone the Repository

```bash
git clone --recurse-submodules https://github.com/Andreaswt/variant-analysis-evo2.git
```

### Install Python

Download and install Python if not already installed. Use the link below for guidance on installation:
[Python Download](https://www.python.org/downloads/)

Create a virtual environment for each folder, except elevenlabs-clone-frontend, with **Python 3.10**.

### Backend

Navigate to backend folder:

```bash
cd evo2-backend
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Modal setup:

```bash
modal setup
```

Run on Modal:

```bash
modal run main.py
```

Deploy backend:

```bash
modal deploy main.py
```

### Frontend

Install dependencies:

```bash
cd evo2-frontend
npm i
```

Run:

```bash
npm run dev
```
