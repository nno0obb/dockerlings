# TODO: Refactor this Dockerfile to use a multi-stage build.
# The goal is to create a final image that is much smaller than this one.

# This single stage uses the full Go SDK, resulting in a large image.
# FROM golang:1.21-alpine
FROM golang:1.21-alpine AS builder

WORKDIR /src

# Copy the source code and build the application
COPY app/ .
RUN go build -o /server .

FROM scratch

COPY --from=builder /server /server

# Expose the port the app runs on
EXPOSE 8080

# The command to run the executable
CMD ["/server"]
