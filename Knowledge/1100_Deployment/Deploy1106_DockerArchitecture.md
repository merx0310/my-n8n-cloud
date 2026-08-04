---
id: Deploy1106
title: Docker Architecture（Docker 部署架構）
category: Deployment
version: 3.0
priority: 11006
layer: Deployment
tags:
  - Docker
  - Docker Compose
  - Deployment
  - Supabase
  - n8n
related:
  - Deploy1105
  - Deploy1107
---

# 建立目的

統一定義 ShuYi-RAG V3.0 Docker 部署架構。

---

# Deployment Architecture

```text
Internet

↓

Nginx

↓

Docker Network

├── n8n
├── OpenWebUI（Optional）
├── PostgreSQL
├── Supabase
├── Redis
├── Qdrant（Optional）
├── MinIO（Optional）
└── Monitoring
```

---

# Docker Compose

建議服務：

```text
nginx

n8n

postgres

redis

supabase

minio

watchtower

portainer
```

---

# Container

## nginx

用途：

Reverse Proxy

HTTPS

Load Balance

---

## n8n

用途：

Workflow

AI Workflow

Webhook

---

## PostgreSQL

用途：

主資料庫

---

## Redis

用途：

Cache

Session

Queue

---

## Supabase

用途：

Authentication

Storage

Vector

Database

---

## MinIO

用途：

Object Storage

Knowledge Backup

Embedding

---

## Watchtower

用途：

Container Auto Update

---

## Portainer

用途：

Docker 管理

---

# Docker Network

固定：

```text
shuyi-network
```

Bridge：

Internal

---

# Volume

固定：

```text
postgres-data

supabase-data

redis-data

n8n-data

minio-data
```

---

# Environment

固定：

```text
.env
```

管理：

```text
OPENAI_API_KEY

SUPABASE_URL

SUPABASE_KEY

POSTGRES_PASSWORD

REDIS_PASSWORD

N8N_ENCRYPTION_KEY
```

---

# Port

建議：

```text
80

443

5678

5432

6379

9000
```

---

# Backup

每日：

```text
Database

↓

Knowledge

↓

Volume

↓

Cloud Backup
```

---

# Security

固定：

HTTPS

Firewall

Environment Secret

Docker Network Isolation

---

# Monitoring

建議：

```text
Prometheus

Grafana

Uptime Kuma
```

---

# Validation

□ Container

□ Network

□ Volume

□ Environment

□ Backup

□ HTTPS

全部正常。

---

# Deployment

支援：

- Ubuntu
- Debian
- Docker Desktop
- VPS
- NAS
- Cloud VM

---

# 關聯

Deploy1105_APIArchitecture

Deploy1107_ProductionArchitecture
