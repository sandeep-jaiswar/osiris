FROM golang:1.19 as builder
WORKDIR /app
COPY . .
RUN go mod download
RUN go build -o producer .

FROM gcr.io/distroless/base-debian11
COPY --from=builder /app/producer /producer
CMD ["/producer"]
