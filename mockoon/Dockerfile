FROM node:20-alpine

ARG version=latest

RUN npm install -g @mockoon/cli@$version

COPY mockoonData.json ./

# Do not run as root.
RUN adduser --shell /bin/sh --disabled-password --gecos "" mockoon
USER mockoon

ENTRYPOINT ["mockoon-cli", "start", "--hostname", "0.0.0.0"]

# Usage: docker run --mount type=bind,source="$(pwd)"/dataFile.json,target=/data,readonly -p <port>:<port> mockoon-test -d data