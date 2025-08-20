# syntax=docker/dockerfile:1
FROM ubuntu:24.04

# Prevent tzdata prompts during install
ENV DEBIAN_FRONTEND=noninteractive

# Install required packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    binutils-arm-none-eabi \
    gcc-arm-none-eabi \
    libnewlib-arm-none-eabi \
    git \
    libpng-dev \
    python3 \
  && rm -rf /var/lib/apt/lists/*

# Set the working directory where the mounted repo will be
WORKDIR /workspace

# Default to an interactive shell
CMD ["/bin/bash"]
