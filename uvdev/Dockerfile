FROM ubuntu:latest

RUN apt-get update \
    && apt-get install -y nala \
    && nala install -y curl git unzip wget

COPY --from=ghcr.io/astral-sh/uv:latest /uv /usr/local/bin/uv
RUN uv python install 3.13 3.12 3.11 3.10 3.9

# Docker container activities

# git config --global user.name "Your Name"
# git config --global user.email "Your Email"

# nala fetch
