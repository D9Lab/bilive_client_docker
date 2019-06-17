FROM i386/node:alpine

MAINTAINER Disappear9

EXPOSE 20080

WORKDIR /app

RUN wget https://github.com/bilive/bilive_server/archive/master.zip \
    && unzip master.zip \
    && mv bilive_server-master/* . \
    && rm -rf bilive_server-master master.zip \
    && mkdir options \
    && cp nedb/roomList.db options/roomList.db \
    && npm install \
    && npm run build

CMD ["sh","-c","npm start"]
