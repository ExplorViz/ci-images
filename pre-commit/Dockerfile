FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y build-essential \
    git-all \
    python3-pip \
    python3 && \
    pip install pre-commit \
    pre-commit install

WORKDIR /pre-commit

CMD ["pre-commit", "run", "--all-files"]
