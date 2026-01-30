FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

ENV DEBIAN_FRONTEND=noninteractive

# 共通ツールのインストール
RUN apt-get update && apt-get install -y \
    curl git unzip zip openjdk-17-jdk \
    && apt-get clean

# Node.js (TypeScript用)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
    && apt-get install -y nodejs \
    && npm install -g typescript ts-node

# Kotlin (SDKMAN)
RUN curl -s "https://get.sdkman.io" | bash \
    && bash -c "source \$HOME/.sdkman/bin/sdkman-init.sh && sdk install kotlin"

# パスを通す（コンテナ起動時に有効化）
ENV PATH="/root/.sdkman/candidates/kotlin/current/bin:${PATH}"
