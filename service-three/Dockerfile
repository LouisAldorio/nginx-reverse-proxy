FROM golang:1.15-alpine as builder

WORKDIR /go/src/myapp

COPY . .

RUN go build -o webserver .


FROM alpine

WORKDIR /app
COPY --from=builder /go/src/myapp/ /app/

CMD ["./webserver"]