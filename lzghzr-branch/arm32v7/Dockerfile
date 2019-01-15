FROM arm32v6/node:alpine

MAINTAINER Disappear9

COPY qemu-arm-static /usr/bin

EXPOSE 23333

WORKDIR /app

RUN wget https://github.com/lzghzr/bilive_client/archive/master.zip \
    && unzip master.zip \
    && mv bilive_client-master/* . \
    && rm -rf bilive_client-master master.zip

RUN npm install \
    && npm run build

CMD ["sh","-c","npm start"]
