FROM node:14-alpine

RUN npm install npm@latest -g && npm install -g ember-cli && npm install -g ember-template-lint

# https://blog.logrocket.com/how-to-set-up-a-headless-chrome-node-js-server-in-docker/

RUN apk update && apk add --no-cache nmap && \
    echo @edge http://nl.alpinelinux.org/alpine/edge/community >> /etc/apk/repositories && \
    echo @edge http://nl.alpinelinux.org/alpine/edge/main >> /etc/apk/repositories && \
    apk update && \
    apk add --no-cache \
      chromium \
      harfbuzz \
      "freetype>2.8" \
      ttf-freefont \
      nss && \
    rm -rf /var/cache/* && \
    mkdir /var/cache/apk

RUN ln -s /usr/bin/chromium-browser /usr/bin/google-chrome
