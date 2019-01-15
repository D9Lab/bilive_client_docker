FROM i386/node:alpine

MAINTAINER Disappear9

EXPOSE 23333

WORKDIR /app

RUN wget https://github.com/Vector000/bilive_client/archive/master.zip \
    && unzip master.zip \
    && mv bilive_client-master/* . \
    && rm -rf bilive_client-master master.zip

RUN npm install \
    && npm run build

CMD ["sh","-c","npm start"]
