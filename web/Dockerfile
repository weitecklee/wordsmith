FROM golang
COPY . .
RUN go build dispatcher.go

FROM ubuntu
COPY --from=0 /go/dispatcher .
CMD ["./dispatcher"]