# Cloud-Native DevOps Microservice

![Build Status](https://github.com/zaidiqbalcode/cloud-native-devops-microservice/actions/workflows/ci-build.yaml/badge.svg)

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Python 3.9](https://img.shields.io/badge/Python-3.9-green.svg)](https://shields.io/)

A production-ready RESTful microservice for managing customer accounts, built with cloud-native principles and DevOps best practices.

## Project Overview

This project demonstrates a complete DevOps implementation of a cloud-native microservice, featuring:

- RESTful Customer Account microservice using Python Flask
- Test Driven Development (TDD) with 95%+ test coverage
- Continuous Integration with GitHub Actions
- Containerization using Docker
- Kubernetes/OpenShift deployment
- Automated CD pipeline using Tekton
- PostgreSQL database integration

## Technologies Used

- **Backend**: Python 3.9, Flask
- **Database**: PostgreSQL
- **CI/CD**: GitHub Actions, Tekton
- **Containerization**: Docker
- **Orchestration**: Kubernetes, OpenShift
- **Testing**: PyTest, TDD methodology
- **Development**: Linux, Agile practices

## Features

- Complete CRUD operations for customer accounts
- RESTful API design following best practices
- Comprehensive test suite with high coverage
- Automated build and deployment pipelines
- Cloud-native architecture
- Production-ready configuration

## Getting Started

### Prerequisites

- Python 3.9 or higher
- Docker
- Kubernetes cluster (optional for local development)
- PostgreSQL

### Installation

1. Clone the repository:
```bash
git clone https://github.com/zaidiqbalcode/cloud-native-devops-microservice.git
cd cloud-native-devops-microservice
```

2. Set up the environment:
```bash
source bin/setup.sh
```

3. Install dependencies:
```bash
make install
```

4. Start the PostgreSQL database:
```bash
make db
```

5. Run the application:
```bash
flask run
```

### Running Tests

Execute the test suite with coverage:

```bash
make test
```

### Docker Deployment

Build and run the Docker container:

```bash
docker build -t account-service .
docker run -p 8080:8080 account-service
```

### Kubernetes Deployment

Deploy to Kubernetes:

```bash
kubectl apply -f deploy/deployment.yaml
kubectl apply -f deploy/service.yaml
```

## Project Structure

```text
├── service/              <- microservice package
│   ├── common/          <- common log and error handlers
│   ├── config.py        <- Flask configuration object
│   ├── models.py        <- persistent model code
│   └── routes.py        <- REST API routes
├── tests/               <- test suite
│   ├── factories.py     <- test factories
│   ├── test_cli_commands.py
│   ├── test_models.py
│   └── test_routes.py
├── deploy/              <- Kubernetes deployment files
│   ├── deployment.yaml
│   ├── service.yaml
│   └── tekton/         <- Tekton pipeline files
├── Dockerfile           <- Container image definition
├── Makefile            <- Build automation
└── requirements.txt    <- Python dependencies
```

## Data Model

The Account model contains the following fields:

| Name | Type | Optional |
|------|------|----------|
| id | Integer| False |
| name | String(64) | False |
| email | String(64) | False |
| address | String(256) | False |
| phone_number | String(32) | True |
| date_joined | Date | False |

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /accounts | List all accounts |
| GET | /accounts/{id} | Get account by ID |
| POST | /accounts | Create new account |
| PUT | /accounts/{id} | Update account |
| DELETE | /accounts/{id} | Delete account |

## CI/CD Pipeline

### GitHub Actions
- Automatic build and test on every push
- Code quality checks
- Test coverage reporting

### Tekton Pipeline
- Automated deployment to Kubernetes
- Zero-downtime deployments
- Production-ready workflows

## Development

This project follows Test Driven Development (TDD) principles. All features are developed with tests written first, ensuring code quality and maintainability.

### Useful Commands

- `make install` - Install Python dependencies
- `make test` - Run test suite
- `make lint` - Run code linting
- `make db` - Start PostgreSQL container
- `make cluster` - Create local K3D cluster
- `make tekton` - Install Tekton locally

## License

Licensed under the Apache License. See [LICENSE](LICENSE)

## Author

Zaid Iqbal
