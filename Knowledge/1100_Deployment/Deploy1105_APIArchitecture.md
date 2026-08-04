---
id: Deploy1105
title: API Architecture（API 系統架構）
category: Deployment
version: 3.0
priority: 11005
layer: Deployment
tags:
  - API
  - REST
  - OpenAI
  - LINE OA
  - n8n
related:
  - Deploy1104
  - Deploy1106
  - Engine1010
---

# 建立目的

統一定義 ShuYi-RAG V3.0 API 架構。

---

# API Flow

```text
Client

↓

API Gateway

↓

Authentication

↓

Permission Engine

↓

Engine1010

↓

Response

↓

Client
```

---

# API Type

支援：

```text
REST API

Webhook

Internal API

Admin API
```

---

# API Endpoint

固定：

```text
POST

/api/chat
```

---

```text
POST

/api/personality
```

---

```text
POST

/api/teacher
```

---

```text
POST

/api/embedding
```

---

```text
POST

/api/search
```

---

```text
GET

/api/version
```

---

```text
GET

/api/health
```

---

# Authentication

支援：

```text
API Key

JWT

OAuth

LINE User ID
```

---

# Request Schema

```json
{
  "user_id":"",
  "role":"",
  "intent":"",
  "question":"",
  "session_id":""
}
```

---

# Response Schema

```json
{
  "status":"success",
  "engine":"Engine1010",
  "response":{},
  "metadata":{}
}
```

---

# HTTP Status

固定：

```text
200 OK

400 Bad Request

401 Unauthorized

403 Forbidden

404 Not Found

429 Too Many Requests

500 Internal Server Error
```

---

# API Timeout

固定：

```text
30 秒
```

---

# Rate Limit

Guest：

```text
20 次 / 小時
```

---

Free：

```text
100 次 / 天
```

---

Member：

```text
1000 次 / 天
```

---

Teacher：

```text
Unlimited
```

---

Admin：

```text
Unlimited
```

---

# API Log

固定：

```json
{
  "request_id":"",
  "user_id":"",
  "endpoint":"",
  "status":"",
  "duration":0,
  "timestamp":""
}
```

---

# Error Response

```json
{
  "status":"error",
  "code":403,
  "message":"Permission Denied"
}
```

---

# API Version

格式：

```text
/v1/

/v2/

/v3/
```

目前：

```text
v3
```

---

# Health Check

Endpoint：

```text
GET

/api/health
```

回傳：

```json
{
  "status":"ok",
  "version":"3.0",
  "engine":"Engine1010"
}
```

---

# Validation

□ Authentication

□ Permission

□ Request

□ Engine

□ Response

□ Log

全部完成。

---

# Deployment

支援：

- LINE Official Account
- Web App
- Mobile App
- n8n
- MCP
- OpenAI API

---

# 關聯

Deploy1104_GitHubArchitecture

Deploy1106_DockerArchitecture

Engine1010_MasterEngine
