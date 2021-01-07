# Use nodejs 15.x offcial image
FROM node:15-alpine

RUN apk update && \
    apk add --no-cache \
    bash \
    curl \
    gnupg

# Install yarn
RUN touch ~/.bashrc \
    && curl -o- -L https://yarnpkg.com/install.sh | bash

# Install Linear Import tool
RUN npm i -g @linear/import
