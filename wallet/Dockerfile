
# FROM alpine:3.11
FROM ubuntu:latest

RUN apt update && \
  apt-get install -y wget curl \
  && rm -rf /var/lib/apt/lists/*

RUN wget -O /usr/local/bin/kepler-wallet https://github.com/keplernetwork/kepler-wallet/releases/download/kepler-3.1.0-beta.2/kepler-wallet-linux && \
  chmod +x /usr/local/bin/kepler-wallet