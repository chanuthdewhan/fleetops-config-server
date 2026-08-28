# FleetOps - Config Server

Part of the **FleetOps Fleet & Logistics Dispatch System**, submitted for the
Enterprise Cloud Architecture (ITS 2130) capstone project.

## Student Information
- **Name:** K.D. Chanuth Dewhan
- **Student ID:** 241722017
- **Slack Handle:** @chanuthdewhan
- **GCP Project ID:** fleet-ops-506803

## Project Description
Centralized configuration server for the FleetOps platform, built on Spring
Cloud Config. All FleetOps microservices fetch their configuration —
database connections, service ports, JWT secrets, storage settings — from
this server at startup, rather than bundling configuration inside each
service's own jar. Configuration is sourced from
[fleetops-config-repo](https://github.com/chanuthdewhan/fleetops-config-repo),
keeping environment-specific settings externalized and version-controlled
separately from application code.

## Technology Stack
- Java 25
- Spring Boot 4.1
- Spring Cloud 2025.1.2 — Config Server
- Spring Boot Actuator

## Setup / Getting Started

```bash
git clone https://github.com/chanuthdewhan/fleetops-config-server.git
cd fleetops-config-server
./mvnw spring-boot:run
```

Runs on port `9000` locally. Requires `fleetops-service-registry` to be
running first for full functionality, and reads configuration from
`fleetops-config-repo`.

## Live Deployment
- **GCP Project ID:** fleet-ops-506803
- **Region:** asia-southeast1
- **Deployment model:** IaaS — Compute Engine, managed via PM2