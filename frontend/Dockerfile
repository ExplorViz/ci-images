FROM node:20.11.0-bookworm

RUN npm install -g ember-cli && npm install -g ember-template-lint

RUN apt update && apt install -y chromium

ENV CHROME_BIN=/usr/bin/chromium \
    CHROME_PATH=/usr/lib/chromium/

RUN ln -s /usr/bin/chromium /usr/bin/google-chrome

RUN groupadd -r chromium && useradd -r -g chromium -G audio,video chromium \
    && mkdir -p /home/chromium/Downloads && chown -R chromium:chromium /home/chromium

# Run as non privileged user since privileged user is not allowed to run chromium without sandbox option
USER chromium
