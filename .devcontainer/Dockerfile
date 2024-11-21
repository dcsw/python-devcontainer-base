

# FROM continuumio/miniconda3 as base
FROM python:3.11-slim as base

# Install system dependencies
RUN apt-get update && apt-get install -y \
    gcc \
    g++ \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

FROM base as base_GCC

# # Upgrade pip and install Python dependencies
# RUN pip install --no-cache-dir --upgrade pip setuptools wheel
# FROM base_GCC as base_GCC_deps

# # Install the latest version of PyMC3 from GitHub
# # RUN pip install --no-cache-dir git+https://github.com/pymc-devs/pymc3
# RUN pip install --no-cache-dir numpy scipy matplotlib pandas pymc ipykernel
FROM base_GCC as base_GCC_deps
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

FROM base_GCC_deps as pymc3

# Add ipykernel to VSCode's python interpretters list for notebook files
RUN python -m ipykernel install --user --name="VSCode-Python3.11.2"

FROM pymc3 as pymc3_vscode

# Set the working directory
WORKDIR /workspace




# # FROM mcr.microsoft.com/devcontainers/anaconda
# # FROM mcr.microsoft.com/devcontainers/python
# FROM python




# FROM python:3.11 as base

# # Install system dependencies
# RUN apt-get update && apt-get install -y \
#     gcc \
#     g++ \
#     && rm -rf /var/lib/apt/lists/*

# FROM base as base_GCC

# # Upgrade pip and install Python dependencies
# RUN pip install --no-cache-dir --upgrade pip
# RUN pip install --no-cache-dir numpy scipy matplotlib pandas jupyter pymc3

# FROM base_GCC as base_GCC_deps

# # Install the latest version of PyMC3 from GitHub
# # RUN pip install --no-cache-dir git+https://github.com/pymc-devs/pymc3

# FROM base_GCC_deps as pymc3

# # Add ipykernel to VSCode's python interpretters list for notebook files
# RUN python -m ipykernel install --user --name="VSCode-Python3.11.2"

# FROM pymc3 as pymc3_vscode

# # Set the working directory
# WORKDIR /workspace




# FROM continuumio/miniconda3

# # Install system dependencies
# RUN apt-get update && apt-get install -y \
#     gcc \
#     g++ \
#     && rm -rf /var/lib/apt/lists/*

# FROM base as base_GCC

# # Upgrade pip and install Python dependencies
# RUN pip install --no-cache-dir --upgrade pip
# RUN pip install --no-cache-dir jupyter pymc3

# FROM base_GCC as base_GCC_deps

# # Install the latest version of PyMC3 from GitHub
# # RUN pip install --no-cache-dir git+https://github.com/pymc-devs/pymc3

# FROM base_GCC_deps as pymc3

# # Add ipykernel to VSCode's python interpretters list for notebook files
# RUN python -m ipykernel install --user --name="VSCode-Python3.11.2"

# FROM pymc3 as pymc3_vscode

# # Set the working directory
# WORKDIR /workspace



# # FROM python:3.9
# FROM continuumio/miniconda3

# # Install system dependencies
# RUN apt-get update && apt-get install -y \
#     gcc \
#     && rm -rf /var/lib/apt/lists/*

# # Install Python dependencies
# RUN pip install --no-cache-dir --upgrade pip
# # RUN pip install --no-cache-dir numpy scipy matplotlib pandas theano ipykernel
# RUN pip install --no-cache-dir numpy scipy matplotlib pandas ipykernel
# # RUN /opt/conda/bin/python -m ipykernel install --user --name="VSCode-Python3.11.2"

# # Set the working directory
# WORKDIR /workspace

# # Install PyMC3
# # RUN pip install --no-cache-dir pymc3
# # RUN conda create -c conda-forge -n pymc_env "pymc>=5"
# # RUN conda activate pymc_env

# # create conda environment
# RUN conda init bash \
#     && . ~/.bashrc \
#     && conda create -c conda-forge -n pymc_env "pymc>=5" \
#     && conda activate pymc_env \
#     && pip install ipython \
#     && /opt/conda/bin/python -m ipykernel install --user --name="VSCode-Python3.11.2"