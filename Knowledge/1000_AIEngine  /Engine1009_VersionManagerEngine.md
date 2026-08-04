---
id: Engine1009
title: Version Manager Engine（版本管理引擎）
category: AIEngine
version: 3.0
priority: 10008
layer: System
tags:
  - Version
  - Release
  - Knowledge
  - AIEngine
  - GitHub
related:
  - Engine1005
  - Engine1008
  - Engine1010
---

# 建立目的

統一管理所有 Knowledge 與 Engine 版本。

---

# Engine流程

```text
Knowledge

↓

Version Check

↓

Status Check

↓

Release

↓

Deploy
```

---

# Version Format

固定：

```text
Major.Minor.Patch
```

例如：

```text
1.0.0

2.0.0

3.0.1
```

---

# Version Rule

Major：

重大更新

Minor：

功能新增

Patch：

錯誤修正

---

# Status

允許：

```text
Draft

Review

Testing

Active

Deprecated

Archive
```

---

# Draft

建立中。

不得部署。

---

# Review

等待審核。

不得部署。

---

# Testing

測試中。

僅測試環境。

---

# Active

正式版本。

允許：

Retrieval。

---

# Deprecated

停止使用。

不得：

Embedding。

不得：

Retrieval。

---

# Archive

封存。

保留歷史版本。

---

# Release Rule

固定：

```text
Draft

↓

Review

↓

Testing

↓

Active
```

---

# Update Policy

Patch：

覆蓋。

Minor：

建立新版本。

Major：

建立新資料夾。

---

# Compatibility

Engine

只能使用：

Active。

不得：

使用：

Deprecated。

---

# Metadata

固定：

```json
{
  "id":"",
  "version":"",
  "status":"",
  "release_date":"",
  "updated_at":""
}
```

---

# Git Tag

格式：

```text
v1.0.0

v2.3.1

v3.0.0
```

---

# Changelog

每次更新：

固定：

```text
Version

Date

Author

Change

Reason
```

---

# Rollback

允許：

Rollback：

上一版。

不得：

Rollback：

Draft。

---

# Retrieval

固定：

搜尋：

最新：

Active。

---

# Validation

□ Version合法

□ Status合法

□ Metadata完整

□ Changelog完成

□ Release完成

---

# Engine Output

```json
{
  "id":"Engine1009",
  "version":"3.0.0",
  "status":"Active",
  "release_date":"",
  "updated_at":""
}
```

---

# 關聯

Engine1005_Metadata

Engine1008_ConversationMemory

Engine1010_MasterEngine
