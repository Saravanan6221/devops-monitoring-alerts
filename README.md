# devops-monitoring-alerts
# DevOps Monitoring and Alerting

## Project

AI Skills Assessment Platform

## Objective

The objective of this task is to monitor EC2 server resources
and backend application health using Prometheus, Node Exporter,
and Blackbox Exporter.

## Problem Statement

When CPU usage reaches 90%, backend response time can increase.
The monitoring system should detect high resource utilization
and application problems and generate alerts.

## Monitoring Components

- Prometheus
- Node Exporter
- Blackbox Exporter
- Prometheus Alert Rules
- Ubuntu EC2
- Backend Application

## Monitoring

### Server Monitoring

Node Exporter monitors:

- CPU
- Memory
- Disk

### Application Monitoring

Blackbox Exporter monitors:

- Backend availability
- HTTP response
- Response time

## Alert Conditions

| Alert | Condition |
|---|---|
| HighCPUUsage | CPU > 90% |
| HighMemoryUsage | Memory > 80% |
| HighDiskUsage | Disk > 80% |
| BackendApplicationDown | Backend unavailable |
| BackendResponseTimeHigh | Response time > 2 seconds |

## Architecture

EC2 Server
    |
    +--> Node Exporter
    |         |
    |         v
    |     Prometheus
    |
    +--> Backend Application
              |
              v
        Blackbox Exporter
              |
              v
          Prometheus
              |
              v
          Alert Rules

## Validation

The following components were tested:

- Prometheus service
- Node Exporter
- Blackbox Exporter
- Backend availability
- CPU alert
- Memory alert
- Disk alert
- Application availability alert
- Response time alert

## Troubleshooting

Refer to:

docs/troubleshooting.md
