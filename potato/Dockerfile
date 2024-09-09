FROM golang:1.23.1 AS builder

WORKDIR /app

COPY go.mod .
COPY go.sum .

RUN go mod download

COPY . .

RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o potato .

FROM alpine:latest AS server

WORKDIR /app

COPY --from=builder /app/potato .

EXPOSE 8080

ENTRYPOINT ["./potato", "8080"]