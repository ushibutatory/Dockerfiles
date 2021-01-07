# Use nodejs 15.x offcial image
FROM node:15-alpine

RUN apk update && \
    apk add --no-cache \
    bash \
    curl \
    gnupg

# Install yarn
# https://github.com/linearapp/linear-import/issues/50
RUN touch ~/.bashrc \
    && curl -o- -L https://yarnpkg.com/install.sh | bash

# Install Linear Import tool
RUN npm i -g @linear/import
