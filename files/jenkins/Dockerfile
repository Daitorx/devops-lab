FROM jenkins/jenkins:lts-jdk17

# Cliente de Docker (y buildx) para que Jenkins construya imágenes usando el Docker del host
COPY --from=docker:cli /usr/local/bin/docker /usr/local/bin/docker
COPY --from=docker:cli /usr/local/libexec/docker/cli-plugins/docker-buildx /usr/local/libexec/docker/cli-plugins/docker-buildx
