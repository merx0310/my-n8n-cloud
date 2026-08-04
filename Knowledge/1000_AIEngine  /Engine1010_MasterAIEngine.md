---
id: Engine1010
title: Master AI Engine（AI 主控引擎）
category: AIEngine
version: 3.0
priority: 99999
layer: System
tags:
  - MasterEngine
  - AI
  - Orchestrator
  - RAG
  - n8n
  - OpenAI
related:
  - Engine1001
  - Engine1002
  - Engine1003
  - Engine1004
  - Engine1005
  - Engine1006
  - Engine1007
  - Engine1008
  - Engine1009
---

# 建立目的

統一調度所有 AI Engine。

---

# Engine流程

```text
User

↓

Engine1002

Permission

↓

Engine1006

Query Router

↓

Engine1005

Metadata

↓

Engine1001

Retrieval

↓

Engine1008

Memory

↓

Engine1004

Prompt Assemble

↓

LLM

↓

Engine1007

Fallback

↓

Engine1003

JSON Output

↓

Response
```

---

# Engine 職責

統一：

- Workflow
- Engine
- Prompt
- Memory
- Retrieval
- JSON
- Response

---

# Engine Priority

固定：

```text
Permission

↓

Query Router

↓

Metadata

↓

Retrieval

↓

Memory

↓

Prompt

↓

LLM

↓

Fallback

↓

JSON
```

---

# Teacher Workflow

```text
Teacher

↓

Permission

↓

Master Retrieval

↓

Memory

↓

Master Prompt

↓

LLM

↓

Teacher Report
```

---

# Free Workflow

```text
Free

↓

Permission

↓

Limited Retrieval

↓

Prompt

↓

LLM

↓

Simple Response
```

---

# Admin Workflow

```text
Admin

↓

All Engine

↓

Debug

↓

Response
```

---

# Engine Control

Master Engine

控制：

```text
Engine1001

↓

Engine1002

↓

Engine1003

↓

Engine1004

↓

Engine1005

↓

Engine1006

↓

Engine1007

↓

Engine1008

↓

Engine1009
```

---

# Engine Input

固定：

```json
{
  "user":{},
  "permission":{},
  "intent":"",
  "question":""
}
```

---

# Engine Output

固定：

```json
{
  "status":"success",
  "engine":"Engine1010",
  "response":{},
  "metadata":{}
}
```

---

# Workflow Rule

任何請求：

不得直接呼叫：

LLM。

必須：

```text
Permission

↓

Router

↓

Retrieval

↓

Prompt

↓

LLM
```

---

# Recovery

任何 Engine

失敗：

固定：

```text
Engine1007
```

處理。

---

# Version

固定：

使用：

最新：

Active

版本。

---

# Logging

每次請求：

固定紀錄：

```json
{
  "request_id":"",
  "user_id":"",
  "intent":"",
  "engine":"Engine1010",
  "status":"",
  "duration":0,
  "timestamp":""
}
```

---

# Validation

□ Permission

□ Router

□ Metadata

□ Retrieval

□ Memory

□ Prompt

□ LLM

□ JSON

全部完成。

---

# Master Rule

所有 AI 回答：

只能透過：

Engine1010。

不得直接呼叫任何單一 Engine。

---

# Deployment

支援：

- ChatGPT
- OpenAI API
- n8n
- LINE OA
- Supabase
- MCP Server
- Web App
- Mobile App

---

# Engine Output Policy

Teacher：

老師版完整人格解析。

Member：

完整功能。

Free：

精簡解析。

Guest：

基本回答。

Admin：

Debug。

---

# AI核心

Master AI Engine

負責：

理解。

調度。

整合。

輸出。

不負責：

知識儲存。

不負責：

Embedding。

不負責：

資料管理。

僅負責：

AI Workflow Orchestration。

---

# 關聯

Engine1001_Retrieval

Engine1002_Permission

Engine1003_JSONSchema

Engine1004_PromptAssembler

Engine1005_Metadata

Engine1006_QueryRouter

Engine1007_Fallback

Engine1008_ConversationMemory

Engine1009_VersionManager
