# https://docs.docker.com/language/golang/build-images/
FROM golang:1.18-alpine AS builder
WORKDIR /usr/src/app
COPY ./hello .
RUN go build hello.go

#https://docs.docker.com/develop/develop-images/baseimages/ (scratch)
FROM scratch
WORKDIR /app
COPY --from=builder /usr/src/app /app
ENTRYPOINT ["./hello"]