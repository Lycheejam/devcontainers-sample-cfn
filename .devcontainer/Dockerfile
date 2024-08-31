ARG IMAGE_REPOSITORY=mcr.microsoft.com/devcontainers/base
ARG IMAGE_TAG=1.1.2-ubuntu-24.04
ARG IMAGE_DIGEST=sha256:523f4f746606453e7c45e546093a7f5744b4ccc066704196a072d54cd4d40f95

FROM ${IMAGE_REPOSITORY}:${IMAGE_TAG}@${IMAGE_DIGEST}

# https://github.com/devcontainers/images/issues/1056
RUN userdel -r ubuntu || true

WORKDIR /opt

ENV RYE_HOME="/opt/rye"
ENV PATH="$RYE_HOME/shims:$PATH"
ARG RYE_VERSION="0.39.0"

# RYE_INSTALL_OPTION is required to build.
# See: https://github.com/mitsuhiko/rye/issues/246
RUN curl -sSf https://rye.astral.sh/get | RYE_VERSION="${RYE_VERSION}" RYE_NO_AUTO_INSTALL=1 RYE_INSTALL_OPTION="--yes" bash
