---
id: Ops1206
title: Knowledge Synchronization Architecture（知識同步架構）
category: Operations
version: 3.0
priority: 12006
layer: Operations
tags:
  - Knowledge
  - Synchronization
  - GitHub
  - Supabase
  - Embedding
related:
  - Ops1205
  - Ops1207
  - Engine1001
  - Engine1005
  - Engine1009
---

# 建立目的

統一定義 ShuYi-RAG V3.0 知識同步流程。

---

# Synchronization Flow

```text
GitHub Repository

↓

Knowledge Update

↓

Validation

↓

Chunk Builder

↓

Metadata Builder

↓

Embedding

↓

Supabase Vector

↓

Knowledge Index

↓

Retrieval Ready
```

---

# Synchronization Source

固定來源：

```text
GitHub Repository
```

唯一知識來源：

```text
Single Source of Truth（SSOT）
```

---

# Synchronization Trigger

支援：

```text
Manual

Git Push

Git Release

Webhook

Scheduled Job
```

---

# Synchronization Scope

同步：

```text
Knowledge

Engine

Prompt

Schema

Deployment

Operations
```

---

# Validation

同步前：

固定檢查：

```text
Markdown Format

Metadata

Version

Status

Duplicate

Reference
```

---

# Chunk Builder

每份文件：

固定：

```text
Document

↓

Chunk

↓

Chunk ID

↓

Chunk Order
```

---

# Metadata Builder

建立：

```text
Category

Module

Role

Priority

Version

Tags

Language

Status
```

---

# Embedding Flow

```text
Chunk

↓

Embedding Model

↓

Vector

↓

Supabase
```

---

# Index Update

完成後：

```text
Update Vector Index

↓

Refresh Cache

↓

Ready
```

---

# Synchronization Mode

支援：

```text
Full Sync

Incremental Sync

Single Document Sync
```

---

# Conflict Policy

若：

Version 衝突：

```text
Latest Active

↓

Review

↓

Replace
```

---

# Failed Synchronization

流程：

```text
Retry

↓

Rollback

↓

Notify Admin
```

最多：

```text
3 次
```

---

# Synchronization Log

```json
{
  "sync_id":"",
  "mode":"Incremental",
  "document_count":0,
  "chunk_count":0,
  "status":"Success",
  "duration":0,
  "timestamp":""
}
```

---

# Validation Checklist

□ Repository

□ Markdown

□ Metadata

□ Chunk

□ Embedding

□ Vector

□ Index

□ Cache

全部完成。

---

# Deployment

支援：

- GitHub
- Supabase
- PostgreSQL
- pgvector
- n8n
- OpenAI Embedding API

---

# 關聯

Ops1205_CRMArchitecture

Ops1207_TokenCostManagement

Engine1001_Retrieval

Engine1005_Metadata

Engine1009_VersionManager
