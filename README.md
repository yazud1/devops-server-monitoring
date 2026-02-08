# DevOps Monitoring Agent

## Overview

This project is part of an **academic DevOps course** at Télécom Saint-Étienne.  
It focuses on the development of a **server monitoring agent**, designed to collect system metrics and expose them through an API for a centralized monitoring dashboard.

The project applies **DevOps principles and practices**, including version control workflows, automated testing, continuous integration, containerization, and deployment.

This repository contains the **agent component** of the global monitoring solution.

---

## Project Goals

The monitoring agent is responsible for:
- Collecting system-level metrics from Linux servers
- Exposing these metrics through a REST API
- Enabling a centralized dashboard to query and display server health information

This agent is intended to be deployed on multiple servers to be monitored.

---

## Features

### System Metrics
- CPU usage (average load)
- RAM usage
- Disk usage
- Network and system information (when available)

### Log Analysis
- Parsing WordPress log files
- Counting error occurrences
- Extracting the most recent error logs
- Identifying most accessed pages

### API
- HTTP API exposing collected metrics
- JSON-formatted responses
- Designed for periodic polling by a monitoring dashboard

---

## Technical Stack

- **Language:** Python
- **API Framework:** Flask / FastAPI (depending on configuration)
- **Testing:** Pytest
- **Linting:** Python linters (flake8 / pylint)
- **CI/CD:** GitLab CI
- **Containerization:** Docker
- **Deployment:** Linux servers (SSH access)

---

## Project Structure

```
agent/
├── src/                    # Agent source code
│   ├── api/                # API endpoints
│   ├── metrics/            # System metrics collectors
│   ├── logs/               # Log parsing logic
│   └── utils/              # Helper functions
├── tests/                  # Unit tests
├── Dockerfile              # Production Docker image
├── Dockerfile-ci           # CI-optimized Docker image
├── .gitlab-ci.yml          # CI pipeline configuration
├── Makefile                # Automation commands
├── requirements.txt        # Production dependencies
├── requirements.dev.txt    # Development dependencies
└── README.md               # Project documentation
```

---

## DevOps Practices

This project applies the following DevOps practices:

- **GitHub / GitLab Flow** branching strategy
- **Continuous Integration**
  - Automated tests
  - Code linting
  - Coverage checks
- **Containerization**
  - Docker images for development, CI, and production
- **Infrastructure Awareness**
  - Designed to run on remote Linux servers
  - Lightweight and easily deployable agent

---

## Installation

### Local Setup

1. Clone the repository:
```
git clone <repository-url>
cd agent
```

2. Install dependencies:
```
pip install -r requirements.txt
```

3. Run the agent:
```
python src/main.py
```

---

## Running with Docker

Build the Docker image:
```
docker build -t monitoring-agent .
```

Run the container:
```
docker run -p 8000:8000 monitoring-agent
```

---

## Continuous Integration

The CI pipeline is defined in `.gitlab-ci.yml` and includes:
- Unit testing
- Linting
- Docker image build
- Validation of merge requests

Only the `main` branch is allowed for production-ready builds.

---

## Limitations

- Simplified monitoring compared to industry tools (Grafana, ELK Stack)
- Designed for educational purposes
- Limited to Linux-based servers

---

## Academic Context

This project was developed as part of a **hands-on DevOps course**.  
It demonstrates:
- DevOps methodology and mindset
- CI/CD pipeline design
- Monitoring concepts
- Infrastructure-aware software development

---

## Authors

Yazid El Mahi

---

## License

This project is developed for **academic purposes only**.  
No commercial use is intended.
