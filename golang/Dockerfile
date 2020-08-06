FROM golang:1.12-alpine as builder

WORKDIR /go/src/app

COPY ./hello.go .

RUN CGO_ENABLED=0 GOOS=linux go build -ldflags="-s -w"

RUN pwd

FROM scratch
WORKDIR /go/src/app
COPY --from=builder /go/src/app/app .

CMD ["./app"]
