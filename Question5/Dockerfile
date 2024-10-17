FROM golang:1.23.2-bookworm AS builder
WORKDIR /app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN go build -o app

FROM gcr.io/distroless/base-debian12
COPY --from=builder /app/app /app
CMD ["/app"]
