FROM golang:1.18-alpine AS builder
WORKDIR /usr/src/app
COPY ./hello .
RUN go build hello.go

#imagem vazia
FROM scratch
WORKDIR /app
COPY --from=builder /usr/src/app /app
ENTRYPOINT ["./hello"]