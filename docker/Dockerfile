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

# Where we'll put the source
WORKDIR /opt

# Copy the source code to the container
COPY . /opt/imperial-purple/

# Navigate to the project directory and build
WORKDIR /opt/imperial-purple
RUN N=$(nproc) && echo "Building with N=${N} jobs..." && make -j"${N}"

# Default to an interactive shell (optional)
CMD ["/bin/bash"]
