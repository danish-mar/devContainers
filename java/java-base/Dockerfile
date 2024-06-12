# Use the Alpine Linux as the base image
FROM alpine:latest

# Install necessary packages for Java development
RUN apk --no-cache add openjdk21 git maven gradle \
    && apk --no-cache add neovim vim nano \
    && apk --no-cache add --virtual build-dependencies curl unzip \
    && curl -sSL https://github.com/zyedidia/micro/releases/download/v2.0.10/micro-2.0.10-linux64.tar.gz | tar -C /usr/local/bin -xz \
    && apk del build-dependencies \
    && rm -rf /var/cache/apk/*

# Set JAVA_HOME environment variable
ENV JAVA_HOME=/usr/lib/jvm/java-21-openjdk

# Set PATH environment variable to include Java and other tools
ENV PATH=$JAVA_HOME/bin:$PATH

# Optional: Set working directory for development projects
WORKDIR /workspace

# Optional: Expose ports if needed
# EXPOSE <port>

# Optional: Define entrypoint if needed
# ENTRYPOINT ["command", "argument1", "argument2", ...]

# Optional: Define default command if needed
# CMD ["command", "argument1", "argument2", ...]

