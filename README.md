# Message Queue

A simple message queue server written in Go. This project demonstrates a basic message queue with pluggable storage backends and a server interface. The queue can be used for learning, prototyping, or as a foundation for more advanced message queue systems.

## Features
- In-memory storage (default, can be extended to disk, S3, etc.)
- Pluggable storage backend via `Storer` interface
- Server abstraction (HTTP, TCP, gRPC can be implemented)
- Simple configuration

## Getting Started

### Prerequisites
- Go 1.18 or newer

### Build

```
make build
```

Or manually:

```
go build -o bin/message_queue main.go
```

### Run

```
./bin/message_queue
```

The server will start on `:3000` by default.

## Project Structure
- `main.go` — Entry point, configures and starts the server
- `server.go` — Server implementation and configuration
- `storage.go` — Storage interface and in-memory implementation
- `storage_test.go` — Unit tests for storage
- `Makefile` — Build commands
- `bin/` — Compiled binaries

## Extending
- Implement new storage backends by satisfying the `Storer` interface
- Add new server protocols (HTTP, TCP, gRPC) in `server.go`

## License
MIT
