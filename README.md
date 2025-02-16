# GoShort - URL Shortener Service

A fast, efficient, and reliable URL shortening service built with Go. GoShort helps you create short, memorable URLs from long, complex ones.

## Features

- Simple URL shortening with REST API
- Automatic redirection to original URLs
- Persistent storage using JSON
- Docker support for easy deployment
- Comprehensive unit tests
- High performance with Go

## Prerequisites

Before you begin, ensure you have the following installed:
- Go (Golang) 1.16 or higher
- Make
- Docker (optional, for containerized deployment)

## Quick Start

1. Clone the repository:
```bash
git clone https://github.com/guptapratykshh/Deveopss.git
cd Deveopss
```

2. Build the application:
```bash
make build
```

3. Run the server:
```bash
make run
```

The server will start at `http://localhost:3002`

## API Documentation

### Base URL
```
http://localhost:3002
```

### Endpoints

#### 1. Create Short URL
Creates a shortened version of the provided URL.

**Request:**
```http
GET /createShortUrl/?url={Long_URL}
```

**Example:**
```http
GET http://localhost:3002/createShortUrl/?url=https://google.com
```

**Response:**
```json
{
    "Url": "http://localhost:3002/shortUrl/2aa789c823074703b7baa8a524eb4aad"
}
```

#### 2. Access Original URL
Redirects to the original URL using the shortened URL.

**Request:**
```http
GET /shortUrl/{shortURL_Path}
```

**Example:**
```http
GET http://localhost:3002/shortUrl/2aa789c823074703b7baa8a524eb4aad
```

**Response:**
Redirects to the original URL (e.g., https://google.com)

## Development

### Available Make Commands

| Command | Description |
|---------|-------------|
| `make build` | Compile the application |
| `make run` | Run the application |
| `make test` | Run unit tests |
| `make image` | Create Docker image |
| `make` | Execute all operations |

### Running Tests

```bash
make test
```

## Docker Deployment

### Option 1: Using Docker Run
```bash
docker run -p 3002:80 --name goshort goshort:latest
```

### Option 2: Using Docker Compose
```bash
docker-compose -f docker-compose.yml up
```

## Project Structure

```
.
├── cmd/            # Application entry point
├── domain/         # Domain models and interfaces
├── endpoint/       # HTTP handlers
├── server/         # Server configuration
├── service/        # Business logic
├── static/         # Static files
└── templates/      # Template files
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

Pratyksh Gupta