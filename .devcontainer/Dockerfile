FROM mcr.microsoft.com/devcontainers/python:3.11

# FFmpeg is useful for video I/O
USER root
RUN apt-get update && apt-get install -y ffmpeg libgl1 && rm -rf /var/lib/apt/lists/*

# Create workspace dir
WORKDIR /workspaces/app

# Pre-install Python deps (optional; devcontainer.json also installs)
COPY requirements.txt /tmp/requirements.txt
RUN pip install --upgrade pip && pip install -r /tmp/requirements.txt

# Keep default non-root user for Codespaces
USER vscode
