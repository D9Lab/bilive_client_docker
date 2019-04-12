FROM node:alpine

MAINTAINER Disappear9

EXPOSE 23333

WORKDIR /app

RUN wget https://github.com/Vector000/bilive_client/archive/master.zip \
    && unzip master.zip \
    && mv bilive_client-master/* . \
    && rm -rf bilive_client-master master.zip \
    && npm install

CMD ["sh","-c","npm start"]

