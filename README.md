# Spring Boot 3 Micrometer Tracing Demo

This project demonstrates Spring Micrometer tracing with Spring Boot 3 running on JDK 21. It includes a Spring MVC controller that calls a service, with SLF4J and Logback logging configured to show traceId and spanId values in log statements.

## Project Structure

- Spring Boot 3.2.0 with JDK 21
- Spring MVC controller and service
- Micrometer tracing with Brave implementation
- SLF4J and Logback for logging with traceId and spanId
- JUnit tests with MockMVC

## Features

- REST endpoint that demonstrates tracing across controller and service
- Logback configuration that includes traceId and spanId in log output
- Comprehensive test suite including unit, integration, and MockMVC tests

## Getting Started

### Prerequisites

- JDK 21
- Maven (or use the included Maven wrapper)

### Running the Application

```bash
./mvnw spring-boot:run
```

### Testing the Application

```bash
./mvnw test
```

## API Endpoints

- `GET /api/process?input=your-input` - Processes the input and returns a result

## Tracing and Logging

The application is configured to include traceId and spanId in all log statements. When you make a request to the API, you'll see log entries with the following pattern:

```
2023-05-27 12:34:56.789 INFO [b4565dc8c9c47dd4,e07ba7ba2714f4a8] --- [nio-8080-exec-1] c.e.demo.controller.DemoController      : Received request in controller with input: test
```

Where:
- `b4565dc8c9c47dd4` is the traceId
- `e07ba7ba2714f4a8` is the spanId

These IDs are propagated between the controller and service, allowing you to trace the request flow through your application.

## Testing with MockMVC

The project includes MockMVC tests that demonstrate how to test the controller and service integration. These tests verify that the controller correctly calls the service and returns the expected response.
