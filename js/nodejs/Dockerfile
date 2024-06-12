# Use the Alpine Linux as the base image
FROM alpine:latest

# Install necessary packages for Node.js development and build tools
RUN apk --no-cache add nodejs npm git python3 make g++ \
    && apk --no-cache add neovim vim nano \
    && apk --no-cache add --virtual build-dependencies curl unzip alpine-sdk bash libstdc++ libc6-compat \
    && curl -sSL https://github.com/zyedidia/micro/releases/download/v2.0.10/micro-2.0.10-linux64.tar.gz | tar -C /usr/local/bin -xz \
    #&& npm config set python python3 \
    #&& npm install -g code-server --unsafe-perm \
    && apk del build-dependencies \
    && rm -rf /var/cache/apk/*

# Optional: Set working directory for development projects
WORKDIR /workspace

# Expose the port code-server runs on
#EXPOSE 8080

# Command to run code-server
#CMD ["code-server", "--bind-addr", "0.0.0.0:8080", "--auth", "none", "."]

