FROM alpine

RUN apk add --update tzdata
ENV TZ=Asia/Shanghai

ENV FRP_VERSION 0.28.2
RUN wget https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_amd64.tar.gz \
    && tar -xzf frp_${FRP_VERSION}_linux_amd64.tar.gz \
    && mkdir /frps \
    && cp frp_${FRP_VERSION}_linux_amd64/frps* /frps/ \
    && rm -rf frp_${FRP_VERSION}_linux_amd64*

RUN rm -rf /var/cache/apk/*

WORKDIR /frps
ENTRYPOINT ["./frps","-c","/frps/frps.ini"]