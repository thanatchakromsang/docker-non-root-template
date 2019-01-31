ARG ALPINE_VERSION=3.8
ARG PYTHON_VERSION=3.7.2
FROM python:${PYTHON_VERSION}-alpine${ALPINE_VERSION}

LABEL maintainer="thanatchakromsang@gmail.com"

ENV APPLICATION_ROOT /app
RUN mkdir $APPLICATION_ROOT

# Create user and group in alpine
RUN addgroup -g 1000 -S app && \
    adduser -u 1000 -S app -G app

# Changer working directory
WORKDIR $APPLICATION_ROOT

# Copy current directory to docker
COPY . .

# Change permission APPLICATION_ROOT folder
RUN chown -R app:app $APPLICATION_ROOT

# Change root to app user
USER app

ENTRYPOINT ["sh", "-c", "python -m http.server 8000"]
