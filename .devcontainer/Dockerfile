FROM ubuntu:22.04

ENV DEBIAN_FRONTEND noninteractive
ENV LANG C.UTF-8
ENV TZ Asia/Tokyo
ENV NVIDIA_DRIVER_CAPABILITIES graphics

RUN apt-get update \
    && apt-get install -y \
    sudo \
    xxd \
    wget \
    curl \
    git \
    xz-utils \
    zip \
    unzip \
    ca-certificates \
    --no-install-recommends 

# Clean Up
RUN	apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* 

# If you want to add vscode user to image, you should comment out the following code
# ARG USERNAME=vscode
# ARG USER_UID=1000
# ARG USER_GID=$USER_UID
# RUN	groupadd --gid $USER_GID $USERNAME \
#     && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
#     && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
#     && chmod 0440 /etc/sudoers.d/$USERNAME \
#     && su $USERNAME \
#     && cd $HOME

# WORKDIR /workspaces
# USER vscode
