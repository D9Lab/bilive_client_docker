FROM alpine AS builder

MAINTAINER Disappear9

RUN apk --no-cache add unzip \
    && wget https://github.com/Disappear9/bilive_client_docker/archive/master.zip \
    && unzip master.zip \
    && mkdir /qemu \
    && cp bilive_client_docker-master/qemu/* /qemu \
    && rm master.zip \
    && wget https://github.com/Vector000/bilive_client/archive/master.zip \
    && unzip master.zip \
    && mkdir /app \
    && mv bilive_client-master/* /app 


FROM arm64v8/node:alpine AS release

COPY --from=builder /qemu/qemu-aarch64-static /usr/bin
COPY --from=builder /app /app

EXPOSE 23333

WORKDIR /app

RUN npm install

CMD ["sh","-c","npm start"]

