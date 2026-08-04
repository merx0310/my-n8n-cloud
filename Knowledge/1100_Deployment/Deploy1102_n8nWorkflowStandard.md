---
id: Deploy1102
title: n8n Workflow Standard（n8n 工作流程規範）
category: Deployment
version: 3.0
priority: 11002
layer: Deployment
tags:
  - n8n
  - Workflow
  - LINE OA
  - OpenAI
  - Supabase
related:
  - Deploy1101
  - Deploy1103
  - Engine1010
---

# 建立目的

統一定義 ShuYi-RAG V3.0 n8n Workflow 標準流程。

---

# Workflow

固定：

```text
Webhook

↓

Verify User

↓

Permission Engine

↓

Query Router

↓

Metadata

↓

Retrieval

↓

Memory

↓

Prompt Assemble

↓

OpenAI

↓

JSON Parser

↓

Reply Message

↓

Log
```

---

# Node 01

Webhook

用途：

接收：

LINE OA

HTTP Request

API

---

# Node 02

Verify User

驗證：

- userId
- token
- role
- status

---

# Node 03

Permission Engine

呼叫：

```text
Engine1002
```

---

# Node 04

Query Router

呼叫：

```text
Engine1006
```

---

# Node 05

Metadata

呼叫：

```text
Engine1005
```

---

# Node 06

Retrieval

呼叫：

```text
Engine1001
```

取得：

Top-K Knowledge

---

# Node 07

Conversation Memory

呼叫：

```text
Engine1008
```

---

# Node 08

Prompt Assemble

呼叫：

```text
Engine1004
```

建立：

完整 Prompt

---

# Node 09

OpenAI

模型：

GPT

輸入：

Prompt

輸出：

Response

---

# Node 10

JSON Parser

呼叫：

```text
Engine1003
```

統一：

JSON Schema

---

# Node 11

Reply

LINE Reply API

Web API

HTTP Response

---

# Node 12

Log

保存：

- User
- Intent
- Engine
- Duration
- Token
- Status

---

# Workflow JSON

固定：

```json
{
  "workflow":"Teacher",
  "version":"3.0",
  "engine":"Engine1010"
}
```

---

# Error Flow

任何節點失敗：

固定：

```text
Engine1007
```

處理。

---

# Timeout

OpenAI：

60秒

Retrieval：

15秒

Supabase：

15秒

Webhook：

30秒

---

# Retry

Retrieval：

3次

OpenAI：

2次

Reply：

2次

---

# Logging

固定：

```json
{
  "workflow":"",
  "node":"",
  "status":"",
  "duration":0,
  "timestamp":""
}
```

---

# Validation

□ Webhook

□ Permission

□ Router

□ Retrieval

□ Memory

□ Prompt

□ OpenAI

□ JSON

□ Reply

□ Log

全部完成。

---

# Deployment

支援：

- LINE Official Account
- Telegram
- Discord
- Web API
- Web App
- Mobile App

---

# 關聯

Deploy1101_DeploymentArchitecture

Deploy1103_SupabaseArchitecture

Engine1010_MasterEngine
