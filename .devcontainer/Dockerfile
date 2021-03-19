FROM node:15.12.0-buster-slim

LABEL org.opencontainers.image.description="Angular devcontainer for VSCode or Codespaces"
LABEL org.opencontainers.image.source=https://github.com/hspaans/angular-devcontainer

EXPOSE 4200

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

# This Dockerfile adds a non-root user with sudo access. Use the "remoteUser"
# property in devcontainer.json to use it. On Linux, the container user's GID/UIDs
# will be updated to match your local UID/GID (when using the dockerFile property).
# See https://aka.ms/vscode-remote/containers/non-root-user for details.
# ARG USERNAME=vscode
# ARG USER_UID=1000
# ARG USER_GID=$USER_UID

COPY package*.json /usr/local/etc/

# Configure apt and install packages
# hadolint ignore=DL3008,DL3016,DL4006,SC2046
RUN apt-get update \
    && apt-get -y install --no-install-recommends apt-utils dialog 2>&1 \
    #
    # Install git iproute2, procps, lsb-release (useful for CLI installs)
    && apt-get -y install --no-install-recommends git iproute2 procps iproute2 lsb-release ca-certificates \
    #
    # Installing Angular CLI
    # && ci npm install -g `grep cli /usr/local/etc/package.json | sed 's/": "/@/;s/"//g'` \
    && npm install -g $(grep cli /usr/local/etc/package.json | sed 's/": "/@/;s/"//g') \
    && echo "export NG_CLI_ANALYTICS=ci" > /etc/profile.d/ng.sh \
    #
    # Create a non-root user to use if preferred - see https://aka.ms/vscode-remote/containers/non-root-user.
    # && groupadd --gid "$USER_GID" "$USERNAME" \
    # && useradd -s /bin/bash --uid "$USER_UID" --gid "$USER_GID" -m "$USERNAME" \
    # [Optional] Add sudo support for the non-root user
    # && apt-get install -y sudo \
    # && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME\
    # && chmod 0440 /etc/sudoers.d/$USERNAME \
    #
    # Clean up
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog

USER node
ENV HOME /home/node
