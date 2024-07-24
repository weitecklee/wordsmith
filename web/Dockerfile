FROM golang
COPY . .
RUN CGO_ENABLED=0 go build dispatcher.go

FROM scratch
COPY --from=0 /go/dispatcher .
CMD ["./dispatcher"]