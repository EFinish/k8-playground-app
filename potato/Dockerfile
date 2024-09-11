FROM golang:1.23.1 AS builder

WORKDIR /app

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o potato .

FROM scratch AS server

WORKDIR /app

COPY --from=builder /app/ .

EXPOSE 8080

ENTRYPOINT ["./potato"]
