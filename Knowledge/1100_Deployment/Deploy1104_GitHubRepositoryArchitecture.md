---
id: Deploy1104
title: GitHub Repository Architecture（GitHub 儲存庫架構）
category: Deployment
version: 3.0
priority: 11004
layer: Deployment
tags:
  - GitHub
  - Repository
  - Knowledge
  - Version
  - Deployment
related:
  - Deploy1103
  - Deploy1105
  - Engine1009
---

# 建立目的

統一定義 ShuYi-RAG V3.0 GitHub Repository 架構。

---

# Repository Structure

```text
ShuYi-RAG/

│
├── Knowledge/
│
│   ├──000_System/
│   ├──100_Algorithm/
│   ├──200_Number/
│   ├──300_MissingNumber/
│   ├──400_FiveElements/
│   ├──500_Star/
│   ├──600_Prompt/
│   ├──700_FiveBlessings/
│   ├──800_LifeCycleAnalysis/
│   ├──900_MasterIntegration/
│   └──1000_AIEngine/
│
├── Deployment/
│
│   ├──1100_Deployment/
│
├── Prompt/
│
│   ├──Teacher/
│   ├──Member/
│   ├──Free/
│   └──System/
│
├── Schema/
│
│   ├──JSON/
│   ├──Metadata/
│   └──Workflow/
│
├── Embedding/
│
├── Scripts/
│
├── Docs/
│
└── README.md
```

---

# Knowledge

用途：

存放所有 Knowledge。

不得：

存放：

Workflow。

JSON。

Script。

---

# Deployment

用途：

部署文件。

例如：

- n8n
- Supabase
- Docker
- Cloud

---

# Prompt

用途：

Prompt 管理。

分類：

```text
Teacher

Member

Free

System
```

---

# Schema

用途：

所有：

JSON

Metadata

Workflow

Schema

---

# Embedding

用途：

Embedding

Chunk

Export

Import

---

# Scripts

用途：

Automation

Migration

Import

Export

Backup

---

# Docs

用途：

技術文件。

API。

Architecture。

Release。

---

# Branch

固定：

```text
main

develop

feature/*

hotfix/*
```

---

# Commit

格式：

```text
feat:

fix:

docs:

refactor:

test:

release:
```

---

# Release

Tag：

```text
v1.0.0

v2.0.0

v3.0.0
```

---

# Ignore

固定：

```text
.env

node_modules

.cache

vector_cache

logs

temp
```

---

# Backup

每日：

```text
GitHub

↓

Release

↓

ZIP Backup
```

---

# Validation

□ Folder

□ README

□ Version

□ Branch

□ Release

□ Ignore

全部完成。

---

# Deployment

Repository：

唯一來源：

Single Source of Truth（SSOT）。

所有：

Knowledge

Engine

Deployment

皆由 GitHub 管理。

---

# 關聯

Deploy1103_SupabaseArchitecture

Deploy1105_APIArchitecture

Engine1009_VersionManager
