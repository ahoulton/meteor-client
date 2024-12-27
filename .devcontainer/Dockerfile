# Use the official Debian image as the base
FROM debian:latest

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive
ENV JAVA_HOME=/usr/lib/jvm/zulu21.38.21-ca-jdk21.0.5-linux_x64
ENV PATH="$JAVA_HOME/bin:$PATH"

# Update package list and install base dependencies
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    curl \
    wget \
    git \
    ca-certificates \
    build-essential \
    apt-utils \
    software-properties-common && \
    mkdir -p /usr/lib/jvm && \
    curl -L -o azul.tar.gz https://cdn.azul.com/zulu/bin/zulu21.38.21-ca-jdk21.0.5-linux_x64.tar.gz && \
    tar -xzf azul.tar.gz -C /usr/lib/jvm && \
    rm azul.tar.gz && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /root

# Default command
CMD ["/bin/bash"]