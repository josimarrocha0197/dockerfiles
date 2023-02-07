FROM golang:latest AS buildando

ENV GO111MODULE=auto

WORKDIR /app
ADD . /app
RUN go build -o meugo

##################################################

FROM alpine:latest
WORKDIR /giropops
COPY --from=buildando /app/meugo /giropops

ENTRYPOINT ./meugo
