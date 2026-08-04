---
id: KB1001
title: RAG 檢索優先順序規則
category: SystemEngine
version: 3.0
priority: 10000
tags:
  - RAG
  - Retrieval
  - Prompt Engine
  - AI
  - System
  - ShuYi
related:
  - KB0910
  - KB1002
  - KB1003
---

# 建立目的

本文件定義：

**ShuYi-RAG V3.0 Retrieval Engine（知識檢索引擎）**

目的不是：

讓 AI 搜尋所有 KB。

而是：

**只搜尋真正需要的知識。**

降低 Token。

提升速度。

提升一致性。

避免不同 KB 同時回答。

---

# Retrieval 原則

AI回答時：

永遠先判斷：

使用者想問什麼。

不是：

先搜尋。

而是：

先分類。

再搜尋。

---

# 第一層分類

收到問題後：

先分類：

```text
A

人格分析

↓

B

人生方向

↓

C

流年

↓

D

幸福人格

↓

E

完整人格

↓

F

知識教學

↓

G

系統問題
```

不得：

直接搜尋全部 KB。

---

# 第二層

依分類：

決定：

搜尋哪些 KB。

---

## A

人格分析

搜尋：

```
KB0101~

KB0501~

KB0411

KB0415
```

---

## B

人生方向

搜尋：

```
KB0601~

KB0606

KB0615
```

---

## C

流年

搜尋：

```
KB0801~

KB0815
```

---

## D

五福

搜尋：

```
KB0701~

KB0715
```

---

## E

完整老師版

搜尋：

```
KB0501~

KB0910
```

全部融合。

---

## F

生命密碼知識

搜尋：

```
KB0101~

KB0415
```

---

## G

系統問題

搜尋：

```
KB1001~

KB1010
```

---

# Retrieval Priority

若：

同時符合多種。

固定優先：

```
0900

Master

＞

0800

流年

＞

0600

夢想

＞

0700

五福

＞

0500

人格

＞

0100

基礎
```

---

# Retrieval Depth

免費版：

最多：

5份 KB。

老師版：

最多：

20份 KB。

Master：

不限。

---

# Query Expansion

例如：

使用者問：

今年如何？

AI應理解：

真正需要：

```
流年

+

主性格

+

夢想

+

五福
```

不是：

只有流年。

---

# Retrieval 禁止事項

不得：

一次搜尋：

全部知識庫。

不得：

全部送給 LLM。

應：

最小知識。

最大效果。

---

# AI Retrieval 流程

```text
User

↓

Intent Detection

↓

Category

↓

KB Selection

↓

Vector Search

↓

Top K

↓

Master Integration

↓

Answer
```

---

# AI品質

檢索：

應：

精準。

快速。

最少 Token。

最大資訊。

---

# AI核心精神

好的 AI，

不是知道最多。

而是：

知道：

什麼時候，

該使用哪一份知識。

---

# 關聯知識

KB0910_Master Prompt Engine

KB1002_權限控制規則

KB1003_JSON Schema
