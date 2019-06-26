FROM alpine AS builder

MAINTAINER Disappear9

RUN apk --no-cache add unzip \
    && wget https://github.com/Disappear9/bilive_client_docker/archive/master.zip \
    && unzip master.zip \
    && mkdir /qemu \
    && cp bilive_client_docker-master/qemu/* /qemu \
    && rm master.zip \

RUN wget https://github.com/bilive/bilive_server/archive/master.zip \
    && unzip master.zip \
    && mkdir bilive_server-master/options \
    && cp bilive_server-master/nedb/roomList.db bilive_server-master/options/roomList.db \
    && mkdir /app \
    && mv bilive_server-master/* /app

FROM arm64v8/node:alpine AS release

COPY --from=builder /qemu/qemu-aarch64-static /usr/bin
COPY --from=builder /app /app

EXPOSE 20080

WORKDIR /app

RUN npm install \
    && npm run build

CMD ["sh","-c","npm start"]
