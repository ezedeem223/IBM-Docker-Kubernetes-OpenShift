# Dockerfile for Guestbook App - Customized by Ezedeen (ezedeem223)
# IBM Final Project: Introduction to Containers w/ Docker, Kubernetes & OpenShift
FROM golang:1.15 as builder
RUN go get github.com/codegangsta/negroni
RUN go get github.com/gorilla/mux github.com/xyproto/simpleredis
COPY main.go .
RUN go build main.go

FROM ubuntu:18.04

COPY --from=builder /go//main /app/guestbook

ADD public/index.html /app/public/index.html
ADD public/script.js /app/public/script.js
ADD public/style.css /app/public/style.css
ADD public/jquery.min.js /app/public/jquery.min.js

WORKDIR /app
CMD ["./guestbook"]
EXPOSE 3000

LABEL maintainer="Ezedeen <ezedeem223@github.com>"
LABEL version="1.0-ezedeen"
LABEL description="Guestbook App - IBM Final Project customized by Ezedeem223"
