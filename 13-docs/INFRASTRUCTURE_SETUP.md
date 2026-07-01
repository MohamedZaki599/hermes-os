# Hermes OS Infrastructure Setup

> Version: 1.0
> Status: Active
> Owner: Mohamed Zaki
> Last Updated: 2026-07-01

---

# Purpose

This document describes how Hermes Infrastructure is built.

It allows rebuilding the production server from scratch.

---

# Production Server

Provider

DigitalOcean

Droplet

Basic Premium Intel

Resources

- 1 vCPU
- 2 GB RAM
- 70 GB SSD
- Ubuntu 24.04 LTS

Hostname

```
hermes-prod-01
```

---

# Server Philosophy

Ubuntu only hosts Docker.

Applications never run directly on Ubuntu.

---

# User Management

Default User

```
root
```

Production User

```
mohamed
```

Root Login

Disabled

Password Authentication

Disabled

SSH Authentication

Enabled

---

# Firewall

UFW

Allowed Ports

22

80

443

Default Policy

Incoming

```
DENY
```

Outgoing

```
ALLOW
```

---

# Docker

Installed from:

Official Docker Repository

Components

- Docker Engine
- Docker Compose
- Buildx
- Containerd

---

# Git

Authentication

SSH

Separate server SSH key

GitHub Authentication

Enabled

---

# Folder Structure

```
/opt/hermes

apps/

configs/

docker/

data/

logs/

workspace/

scripts/

backups/
```

---

# Applications

```
apps/

hermes-os/

hermes-agent/
```

---

# Docker Services

Current

- PostgreSQL
- Redis
- Qdrant
- Caddy

Future

- Grafana
- Prometheus
- Loki

---

# Security Decisions

SSH Keys only

No Password Login

No Root Login

Firewall Enabled

Dedicated Server SSH Key

Official Docker Packages

---

# Backup Strategy

Directories

```
backups/
```

Future

- PostgreSQL backups
- Configuration backups
- Workspace snapshots

---

# Monitoring

Future

- Grafana
- Prometheus
- Loki

---

# Disaster Recovery

A new server should be reproducible using:

1. Ubuntu
2. Docker
3. Git
4. Clone repositories
5. Restore backups
6. Start Docker Compose

Target recovery time:

Less than 30 minutes.

---

# Infrastructure Principles

- Immutable Infrastructure
- Docker-first
- SSH-only access
- Documentation first
- Security by default
- Modular services
- Production-ready from day one

---

# Changelog

## 2026-07-01

- VPS Created
- Ubuntu Installed
- SSH Configured
- Root Login Disabled
- Password Login Disabled
- Docker Installed
- Git Configured
- Firewall Enabled
- GitHub Connected
- Hermes Platform Initialized

---

# End of Document