FROM golang:alpine as servicewa
WORKDIR /usr/local
RUN apk add --no-cache git
RUN apk add --update bash
ENV GO_VERSION=1.14.3
ENV GOPATH /go
ENV GOBIN /go/bin
ENV PATH /usr/local/go/bin:/go/bin:$PATH
WORKDIR /code/serviceSendTextMessage
COPY serviceSendTextMessage .
RUN ls
RUN go get .
RUN go build .
RUN mkdir /tmp/WhatsAppSession/
