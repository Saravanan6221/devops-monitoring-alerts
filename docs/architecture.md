# Monitoring Architecture

## Objective

The objective of this monitoring setup is to monitor server resources
and backend application availability.

## Architecture Flow

EC2 Server
    |
    +-- Node Exporter
    |       |
    |       v
    |   Prometheus
    |
    +-- Backend Application
            |
            v
      Blackbox Exporter
            |
            v
        Prometheus
            |
            v
       Alert Rules

## Components

### Node Exporter

Node Exporter collects EC2 server metrics such as:

- CPU usage
- Memory usage
- Disk usage

### Blackbox Exporter

Blackbox Exporter checks the backend application through HTTP.

It helps monitor:

- Application availability
- HTTP response
- Response time

### Prometheus

Prometheus collects metrics from Node Exporter and Blackbox Exporter.

Prometheus also evaluates the alert rules.

## Alerts

The monitoring system contains alerts for:

- CPU usage above 90%
- Memory usage above 80%
- Disk usage above 80%
- Backend application unavailable
- Backend response time above 2 seconds
