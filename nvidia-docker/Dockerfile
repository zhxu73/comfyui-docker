FROM nvcr.io/nvidia/cuda:13.0.3-cudnn-devel-ubuntu24.04

ARG COMFYUI_VERSION=v0.24.1

RUN DEBIAN_FRONTEND=noninteractive apt update -qq && apt install -y \
  python3 python3-venv python3-pip python3-dev \
  build-essential pkg-config git curl ca-certificates \
  ffmpeg \
  libgl1 libegl1 libgles2 libglu1-mesa libglib2.0-0t64 \
  libglfw3 \
  libgomp1 \
  libsndfile1 \
  zlib1g libjpeg-turbo8 libpng16-16 libtiff6 libwebp7 \
  libopenjp2-7 libfreetype6 liblcms2-2

RUN git clone --branch ${COMFYUI_VERSION} --single-branch https://github.com/Comfy-Org/ComfyUI.git /opt/ComfyUI && \
  pip3 install --break-system-packages -r /opt/ComfyUI/requirements.txt

USER ubuntu

CMD ["python3", "/opt/ComfyUI/main.py"]

