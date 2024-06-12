# Use the Alpine Linux as the base image
FROM alpine:latest

# Install necessary packages for Python development
RUN apk --no-cache add python3 py3-pip git \
    && apk --no-cache add neovim vim nano \
    && apk --no-cache add --virtual build-dependencies curl unzip alpine-sdk bash libstdc++ libc6-compat \
    && curl -sSL https://github.com/zyedidia/micro/releases/download/v2.0.10/micro-2.0.10-linux64.tar.gz | tar -C /usr/local/bin -xz \
    && apk del build-dependencies \
    && rm -rf /var/cache/apk/*

# Upgrade pip and install virtualenv
RUN pip3 install --break-system-packages --upgrade pip \
    && pip3 install --break-system-packages virtualenv

# Optional: Set working directory for development projects
WORKDIR /workspace

# Optional: Expose ports if needed
# EXPOSE <port>

# Optional: Define entrypoint if needed
# ENTRYPOINT ["command", "argument1", "argument2", ...]

# Optional: Define default command if needed
# CMD ["command", "argument1", "argument2", ...]

