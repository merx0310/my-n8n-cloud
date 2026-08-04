---
id: Deploy1101
title: Deployment Architecture（系統部署架構）
category: Deployment
version: 3.0
priority: 11001
layer: Deployment
tags:
  - Deployment
  - n8n
  - Supabase
  - OpenAI
  - LINE OA
related:
  - Engine1010
  - Deploy1102
---

# 建立目的

統一定義 ShuYi-RAG V3.0 系統部署架構。

---

# 系統架構

```text
LINE OA

↓

Webhook

↓

n8n

↓

Engine1010

↓

OpenAI

↓

Supabase Vector

↓

Knowledge

↓

Response

↓

LINE OA
```

---

# 系統元件

```text
LINE Official Account

n8n

OpenAI API

Supabase

GitHub

Knowledge Repository
```

---

# n8n職責

- 接收 Webhook
- 使用者驗證
- 權限判斷
- 呼叫 Engine1010
- 回傳結果
- 紀錄 Log

---

# OpenAI職責

- Prompt 執行
- 推理
- 生成回答

---

# Supabase職責

- Vector Search
- Metadata
- Embedding
- Conversation Data

---

# GitHub職責

- Knowledge Version
- Engine Version
- Release
- Backup

---

# 資料流程

```text
User

↓

LINE OA

↓

Webhook

↓

n8n

↓

Permission

↓

Retrieval

↓

OpenAI

↓

JSON

↓

LINE Reply
```

---

# Validation

□ Webhook正常

□ Engine正常

□ OpenAI正常

□ Supabase正常

□ Reply正常

---

# 關聯

Engine1010_MasterEngine

Deploy1102_n8nWorkflow
