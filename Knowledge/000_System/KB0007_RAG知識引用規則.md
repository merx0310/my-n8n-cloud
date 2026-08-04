---
id: KB0007
title: RAG知識引用規則
category: System
version: 2.0
priority: 100
tags:
  - RAG
  - Retrieval
  - KnowledgeBase
  - AI
related:
  - KB0001
  - KB0002
  - KB0004
  - KB0110
---

# RAG知識引用規則

本知識庫採用 Retrieval-Augmented Generation（RAG）架構。

AI回答時，不得一次讀取全部知識。

而是依照問題，自動搜尋最相關的知識，再重新組合回答。

目的：

提高回答速度。

降低錯誤率。

避免引用不相關內容。

---

# 搜尋順序

AI依照以下順序搜尋知識：

第一步

搜尋主性格。

例如：

9號人

取得：

KB0209

---

第二步

搜尋缺數。

例如：

缺4

缺6

取得：

KB0304

KB0306

---

第三步

搜尋特殊組合。

例如：

缺4＋缺6

取得：

KB0310

若沒有特殊組合，

略過。

---

第四步

搜尋系統規則。

例如：

回答方式。

免費版限制。

文章格式。

取得：

KB0001

KB0002

KB0003

KB0006

---

第五步

重新整合文章。

不得直接貼出知識內容。

必須重新組織。

---

# 知識引用原則

AI每次回答，

優先引用：

最相關知識。

引用數量建議：

3～8篇。

避免：

一次引用過多知識。

造成回答冗長。

---

# 關聯知識

每篇Markdown皆須建立：

related

例如：

related:

KB0206

KB0306

KB0310

KB0401

AI可依據 related 持續擴展搜尋。

---

# Tags規則

每篇Markdown必須建立tags。

例如：

tags:

- 主性格

- 六號人

- 財富

- 金

- 五行

- 免費版

AI可利用Tags提高搜尋準確率。

---

# Priority規則

priority：

100

代表：

核心知識。

例如：

系統規則。

演算法。

九大人格。

priority：

80

代表：

一般知識。

例如：

五行。

左右星。

priority：

60

代表：

案例。

QA。

Prompt。

AI搜尋時，

優先取得Priority較高內容。

---

# 回答禁止事項

AI不得：

一次引用整本知識庫。

不得：

將Markdown原文輸出。

不得：

逐條背誦知識。

知識庫用途：

提供AI理解。

不是提供使用者閱讀。

---

# Chunk規則

每篇Markdown：

建議：

500～1500字。

一篇只說一件事。

不得：

一篇放太多主題。

避免降低RAG搜尋品質。

---

# Metadata標準

所有Markdown必須包含：

id

title

category

version

priority

tags

related

方便：

Supabase

OpenAI Vector Store

Pinecone

Milvus

Weaviate

Qdrant

Dify

LangChain

Flowise

等RAG系統建立Embedding。

---

# AI回答目標

AI透過RAG取得知識後，

必須重新理解。

重新組織。

重新表達。

回答必須像老師。

不得像搜尋引擎。

不得像知識庫。

不得像維基百科。

---

# 關聯知識

KB0001_AI角色設定

KB0002_AI回答規則

KB0004_AI回答流程

KB0006_文章輸出格式

KB0110_人格判讀流程
