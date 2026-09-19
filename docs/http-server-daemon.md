---
id: "http-server-daemon"
title: "Networking: HTTP Server & APIs"
category: "Standard Library"
level: "Beginner"
summary: "Building high-throughput microservices, REST APIs, and JSON web servers with HttpServer."
tags:
  - blazelang
  - docs
codeExample: "Import HttpServer from \"http\"\nImport Json from \"json\"\n\nvar server = HttpServer.Create(8080)\n\nserver.Use(Function(req, res, next) {\n    Show(req.Method + \" \" + req.Path)\n    next()\n})\n\nserver.Get(\"/\", Function(req, res) {\n    res.Send(\"BlazeLang API\")\n})\n\nserver.Get(\"/api/status\", Function(req, res) {\n    var status = {\n        status: \"healthy\",\n        version: \"2.3\",\n        runtime: \"native\"\n    }\n\n    res.Header(\"Content-Type\", \"application/json\")\n    res.Send(Json.Stringify(status))\n})\n\nserver.Get(\"/api/users/:id\", Function(req, res) {\n    var response = {\n        id: req.Params.id,\n        found: true\n    }\n\n    res.Header(\"Content-Type\", \"application/json\")\n    res.Send(Json.Stringify(response))\n})\n\nserver.Post(\"/api/users\", Function(req, res) {\n    var user = Json.Parse(req.Body)\n\n    var response = {\n        success: true,\n        name: user.name\n    }\n\n    res.Status(201)\n    res.Header(\"Content-Type\", \"application/json\")\n    res.Send(Json.Stringify(response))\n})\n\nserver.Listen()"
---

# BlazeLang Native HTTP Server

BlazeLang includes a built-in native HTTP server designed for building REST APIs, backend services, local development servers, webhooks, and lightweight network applications without requiring an external web framework.

The server integrates directly with the BlazeLang runtime and supports routing, HTTP methods, request data, response headers, status codes, JSON APIs, middleware, and concurrent request handling.

---

## Creating a REST Server

A basic BlazeLang HTTP server can be created with `HttpServer`:

```blaze
Import HttpServer from "http"
Import Json from "json"

var server = HttpServer.Create(8080)

server.Get("/", Function(req, res) {
    res.Send("Welcome to BlazeLang Native HTTP Server!")
})

server.Get("/api/status", Function(req, res) {
    var data = {
        status: "healthy",
        version: "2.3",
        uptime: 3600
    }

    res.Header("Content-Type", "application/json")
    res.Send(Json.Stringify(data))
})

Show("Server listening on http://localhost:8080")
server.Listen()
```

Run the program and the server will begin listening on port `8080`.

---

## HTTP Routes

BlazeLang provides route registration for common HTTP methods.

```blaze
server.Get("/users", Function(req, res) {
    res.Send("User list")
})

server.Post("/users", Function(req, res) {
    res.Status(201)
    res.Send("User created")
})

server.Put("/users/1", Function(req, res) {
    res.Send("User updated")
})

server.Delete("/users/1", Function(req, res) {
    res.Send("User deleted")
})
```

### Supported Methods

* `GET`
* `POST`
* `PUT`
* `PATCH`
* `DELETE`

---

## Working With Requests

The request object provides information about an incoming HTTP request.

```blaze
server.Get("/info", Function(req, res) {
    Show(req.Method)
    Show(req.Path)
    Show(req.Body)

    res.Send("Request received")
})
```

Request data can be used to build APIs that respond dynamically to incoming clients.

### Query Parameters

Query parameters can be accessed through the request object.

For example:

`http://localhost:8080/search?q=blazelang`

```blaze
server.Get("/search", Function(req, res) {
    var query = req.Query.q

    res.Send("Searching for: " + query)
})
```

### Route Parameters

Dynamic routes can be used when an API needs to work with specific resources.

```blaze
server.Get("/users/:id", Function(req, res) {
    var id = req.Params.id

    res.Send("Requested user: " + id)
})
```

For a request such as:

`GET /users/42`

the route parameter contains `42`.

---

## JSON APIs

BlazeLang's JSON module can be combined with the HTTP server to create JSON-based APIs.

```blaze
Import Json from "json"

server.Get("/api/user", Function(req, res) {
    var user = {
        id: 1,
        name: "Rohit",
        language: "BlazeLang"
    }

    res.Header("Content-Type", "application/json")
    res.Send(Json.Stringify(user))
})
```

The endpoint returns:

```json
{
    "id": 1,
    "name": "Rohit",
    "language": "BlazeLang"
}
```

### POST Requests and Request Bodies

POST endpoints can process request bodies.

For JSON requests, the body can be parsed using `Json.Parse()`:

```blaze
Import Json from "json"

server.Post("/api/users", Function(req, res) {
    var data = Json.Parse(req.Body)

    Show(data.name)

    var response = {
        success: true,
        message: "User created"
    }

    res.Status(201)
    res.Header("Content-Type", "application/json")
    res.Send(Json.Stringify(response))
})
```

---

## Response Headers and Status Codes

### Response Headers

Response headers can be configured using `res.Header()`.

```blaze
server.Get("/api/data", Function(req, res) {
    res.Header("Content-Type", "application/json")
    res.Header("Cache-Control", "no-cache")

    res.Send("{\"status\":\"ok\"}")
})
```

### HTTP Status Codes

Use `res.Status()` to return an appropriate HTTP status code.

```blaze
server.Get("/api/missing", Function(req, res) {
    res.Status(404)
    res.Send("Resource not found")
})
```

Common status codes include:

| Status | Meaning               |
| ------ | --------------------- |
| `200`  | OK                    |
| `201`  | Created               |
| `400`  | Bad Request           |
| `401`  | Unauthorized          |
| `403`  | Forbidden             |
| `404`  | Not Found             |
| `500`  | Internal Server Error |

---

## Middleware

Middleware can be used for logic that should run before request handlers.

Typical use cases include:

* Authentication
* Request logging
* Validation
* Rate limiting
* CORS
* Request tracing

Example:

```blaze
server.Use(Function(req, res, next) {
    Show(req.Method + " " + req.Path)
    next()
})
```

---

## Concurrent Request Handling

The native HTTP server is designed to handle multiple incoming requests concurrently.

This makes it suitable for:

* REST APIs
* Backend services
* Microservices
* Local development servers
* Webhook receivers
* Package registry services
* Developer tools
* Local AI services

For performance-sensitive applications, avoid unnecessary blocking operations inside request handlers.

---

## Complete Example

The following example combines routing, middleware, JSON responses, dynamic parameters, and POST requests into a small REST API.

```blaze
Import HttpServer from "http"
Import Json from "json"

var server = HttpServer.Create(8080)

server.Use(Function(req, res, next) {
    Show(req.Method + " " + req.Path)
    next()
})

server.Get("/", Function(req, res) {
    res.Send("BlazeLang API")
})

server.Get("/api/status", Function(req, res) {
    var status = {
        status: "healthy",
        version: "2.3",
        runtime: "native"
    }

    res.Header("Content-Type", "application/json")
    res.Send(Json.Stringify(status))
})

server.Get("/api/users/:id", Function(req, res) {
    var response = {
        id: req.Params.id,
        found: true
    }

    res.Header("Content-Type", "application/json")
    res.Send(Json.Stringify(response))
})

server.Post("/api/users", Function(req, res) {
    var user = Json.Parse(req.Body)

    var response = {
        success: true,
        name: user.name
    }

    res.Status(201)
    res.Header("Content-Type", "application/json")
    res.Send(Json.Stringify(response))
})

server.Listen()
```

---

## Performance

The BlazeLang HTTP server is implemented as part of the native runtime, reducing the need for an additional web framework between the application and the server layer.

Actual latency and throughput depend on hardware, operating system, network conditions, request size, concurrency, and application logic. Production deployments should benchmark the server using workloads representative of the intended application.

---

## Security

The HTTP server provides networking primitives, while application-level security remains the responsibility of the developer.

Production APIs should consider:

* Authentication and authorization
* Input validation
* Request-size limits
* Rate limiting
* Secure CORS configuration
* TLS
* Secret management
* Error handling
* Protection against malformed requests

Sensitive internal information should not be exposed through API error responses.

---

## Conclusion

BlazeLang's native HTTP server provides a direct way to build network services and REST APIs using the language's native runtime.

With routing, JSON support, request handling, middleware, HTTP status codes, and concurrent request processing, BlazeLang can be used for applications ranging from small local services to larger backend components.
