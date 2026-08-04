---
id: Deploy1103
title: Supabase Architecture（Supabase 系統架構）
category: Deployment
version: 3.0
priority: 11003
layer: Deployment
tags:
  - Supabase
  - PostgreSQL
  - pgvector
  - Embedding
  - Vector Search
related:
  - Deploy1102
  - Deploy1104
  - Engine1001
  - Engine1005
---

# 建立目的

統一定義 ShuYi-RAG V3.0 Supabase 資料架構。

---

# System Architecture

```text
GitHub

↓

Knowledge

↓

Embedding

↓

Supabase

↓

pgvector

↓

Retrieval

↓

OpenAI
```

---

# Database

固定：

```text
PostgreSQL

+

pgvector
```

---

# Table

固定：

```text
documents

chunks

embeddings

metadata

users

conversation

projects

logs
```

---

# documents

用途：

Knowledge 原始文件。

---

## Schema

```text
id

title

module

version

status

created_at

updated_at
```

---

# chunks

用途：

Chunk 資料。

---

## Schema

```text
chunk_id

document_id

content

chunk_order

token_count
```

---

# embeddings

用途：

Vector。

---

## Schema

```text
embedding_id

chunk_id

embedding

model

dimension

created_at
```

---

# metadata

用途：

Retrieval Filter。

---

## Schema

```text
document_id

category

module

role

priority

tags

language

status
```

---

# users

用途：

會員資料。

---

## Schema

```text
user_id

role

status

created_at

updated_at
```

---

# conversation

用途：

Memory。

---

## Schema

```text
conversation_id

user_id

session_id

question

answer

created_at
```

---

# projects

用途：

Project Memory。

---

## Schema

```text
project_id

user_id

name

status

updated_at
```

---

# logs

用途：

Engine Log。

---

## Schema

```text
log_id

engine

workflow

status

duration

timestamp
```

---

# Vector Search

固定：

```text
Metadata Filter

↓

Similarity Search

↓

Top-K

↓

Chunk Merge
```

---

# Embedding

建議：

```text
text-embedding-3-small
```

或：

```text
text-embedding-3-large
```

---

# Similarity

固定：

```text
Cosine Similarity
```

---

# Index

固定：

```text
HNSW
```

---

# Backup

每日：

Database Backup

↓

GitHub Release

↓

Storage Backup

---

# Validation

□ documents

□ chunks

□ embeddings

□ metadata

□ users

□ conversation

□ projects

□ logs

全部正常。

---

# Deployment

支援：

- Supabase Cloud
- Self-host PostgreSQL
- pgvector

---

# 關聯

Deploy1102_n8nWorkflow

Deploy1104_GitHubArchitecture

Engine1001_Retrieval

Engine1005_Metadata
