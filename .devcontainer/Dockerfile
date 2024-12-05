

# FROM continuumio/miniconda3 as base
FROM python:3.11-slim as base

# Install system dependencies
RUN apt-get update && apt-get install -y \
    gcc \
    g++ \
    python3-dev \
    texlive-xetex texlive-fonts-recommended texlive-plain-generic \
    graphviz \
    && rm -rf /var/lib/apt/lists/*

FROM base as base_GCC

# # Upgrade pip and install Python dependencies
RUN pip install --no-cache-dir --upgrade pip setuptools wheel

FROM base_GCC as base_GCC_deps
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

FROM base_GCC_deps as pymc3

FROM pymc3 as pymc3_vscode

# Set the working directory
WORKDIR /workspace