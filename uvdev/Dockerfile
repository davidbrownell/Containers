FROM ubuntu:latest

RUN apt-get update \
    && apt-get install -y nala \
    && nala install -y curl git unzip wget \
    && apt clean

COPY --from=ghcr.io/astral-sh/uv:latest /uv /usr/local/bin/uv

# These environment variables control where uv stores its data. When creating a container from this
# image, you can mount a volume to these directories to persist the data across container restarts.
# If you don't mount a volume, the `/host` directory will still be used to store the data but any
# changes will be lost when the container is removed.

ENV UV_CACHE_DIR=/host/uv/cache
ENV UV_PYTHON_INSTALL_DIR=/host/uv/python
ENV UV_TOOL_DIR=/host/uv/tools

RUN uv python install 3.14 3.13 3.12 3.11 3.10

# ----------------------------------------------------------------------
# Docker container activities

# nala fetch

# git config --global user.name "Your Name"
# git config --global user.email "Your Email"
