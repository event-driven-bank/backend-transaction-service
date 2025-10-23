> The `backend-transaction-service` is a core component responsible for initiating and validating financial transactions. It serves as the **command-side** of our event-driven architecture, receiving transaction requests, performing initial business validations, and publishing a event for asynchronous processing.


# Architectural Overview: Ports & Adapters

This service is built using **Hexagonal Architecture** to ensure a clean separation between the core business logic and external technologies.

**The Application Core:** Located in `internal/application/service/`. It contains all the business rules and logic.

**Ports:** These are Go `interfaces` defined in `internal/application/port`. They act as the contracts that define how information flows in and out of the application core.

**Adapter:** Define how external clients can interact _with_ our `Transaction Domain`


# Directory Structure

```
backend-transaction-service/
├── cmd/api/
│   └── main.go
│
├── internal/
│   ├── application/
│   │   ├── port/
│   │   │   ├── primary.go
│   │   │   └── secondary.go
│   │   │
│   │   └── service/
│   │       └── transaction_service.go
│   │
│   └── adapter/
│       └── http/
│           └── transaction_handler.go
│
└── .gitignore
└── README
```

# Getting Started

## Prerequisites

- Go 1.18+

## Run

```sh
go run
```

## Build

```sh
go build -o app ./cmd/api
```
