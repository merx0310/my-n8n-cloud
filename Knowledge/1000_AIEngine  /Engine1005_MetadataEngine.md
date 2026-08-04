---
id: Engine1005
title: Metadata Engine（Metadata 管理引擎）
category: AIEngine
version: 3.0
priority: 10004
layer: System
tags:
  - Metadata
  - Embedding
  - Vector
  - Supabase
  - AIEngine
related:
  - Engine1001
  - Engine1003
  - Engine1004
  - Engine1006
---

# 建立目的

統一所有 Knowledge Metadata。

---

# Engine流程

```text
Knowledge

↓

Metadata Builder

↓

Embedding

↓

Vector Database

↓

Search
```

---

# Metadata Schema

固定：

```json
{
  "id":"",
  "title":"",
  "category":"",
  "module":"",
  "version":"",
  "role":"",
  "tags":[],
  "priority":0,
  "status":"",
  "language":"",
  "embedding":true
}
```

---

# id

例如：

```text
KB0508

Engine1001
```

---

# title

例如：

```text
G位人格判讀規則

Retrieval Engine
```

---

# category

允許：

```text
Knowledge

Algorithm

Personality

Dream

FiveBlessings

LifeCycle

MasterIntegration

AIEngine
```

---

# module

例如：

```text
500_Star

600_Prompt

900_MasterIntegration

1000_AIEngine
```

---

# version

例如：

```text
3.0
```

---

# role

允許：

```text
Guest

Free

Member

Teacher

Admin
```

---

# tags

例如：

```json
[
  "人格",
  "流年",
  "RAG"
]
```

---

# priority

範圍：

```text
1~10000
```

---

# status

允許：

```text
draft

active

deprecated

archive
```

---

# language

例如：

```text
zh-TW
```

---

# embedding

```text
true

false
```

---

# Chunk Metadata

每個 Chunk

必須包含：

```json
{
  "chunk_id":"",
  "document_id":"",
  "order":1,
  "tokens":0
}
```

---

# Search Filter

固定：

```text
Role

↓

Category

↓

Module

↓

Version

↓

Status
```

---

# Embedding Rule

status：

active

且：

embedding=true

才允許建立 Vector。

---

# Deprecated

```text
deprecated

archive
```

不得加入 Retrieval。

---

# Metadata Example

```json
{
  "id":"KB0812",
  "title":"流年與主性格融合判讀規則",
  "category":"LifeCycle",
  "module":"800_LifeCycleAnalysis",
  "version":"3.0",
  "role":"Teacher",
  "tags":[
    "流年",
    "人格"
  ],
  "priority":900,
  "status":"active",
  "language":"zh-TW",
  "embedding":true
}
```

---

# Validation

□ id存在

□ category合法

□ module合法

□ version存在

□ role存在

□ status合法

□ embedding合法

---

# Engine Output

Metadata JSON

↓

Embedding

↓

Supabase Vector

---

# 關聯

Engine1001_Retrieval

Engine1003_JSONSchema

Engine1004_PromptAssembler

Engine1006_QueryRouter
