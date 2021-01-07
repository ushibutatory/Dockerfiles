# Use nodejs 15.x image in DockerHub
FROM node:latest

ENV APT_KEY_DONT_WARN_ON_DANGEROUS_USAGE DontWarn
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    curl \
    apt-transport-https \
    apt-utils

# Install yarn
# https://github.com/linearapp/linear-import/issues/50
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    yarn
RUN yarn install && \
    yarn -v

RUN apt-get clean -y

# Install Linear Import tool
RUN npm i -g @linear/import
