from golang:1.16

WORKDIR /go_app

# Copy the code into the container
COPY app_v1.go /go_app

# Build Go binary
RUN go build app_v1.go

# Exposes aplication port on container 8090
EXPOSE 8090

# Run Go binary
ENTRYPOINT ["/go_app/app_v1"]