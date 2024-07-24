FROM golang:alpine
COPY . .
RUN CGO_ENABLED=0 go build dispatcher.go

FROM alpine
COPY --from=0 /go/dispatcher .
CMD ["./dispatcher"]