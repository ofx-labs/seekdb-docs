# SeekDB Documentation Index

Complete documentation index for SeekDB vector database.

---

## 1. Developer Guide

**Location**: `seekdb-docs/developer-guide/zh/` (Chinese) and `seekdb-docs/developer-guide/en/` (English)  
**Document Count**: 12 documents × 2 languages = 24 documents  
**Overview**:
- For SeekDB contributors and core developers
- Covers complete development workflow from environment setup to core system design
- Includes coding standards, testing, debugging, and system architecture

### 1.1 Entry Point

- **README.md** - Developer guide overview
  - Chinese: `seekdb-docs/developer-guide/zh/README.md`
  - English: `seekdb-docs/developer-guide/en/README.md`
  - Purpose: Overview of developer guide structure and learning path

### 1.2 Environment Setup (3 documents)

- **toolchain.md** - Install toolchain
  - Chinese: `seekdb-docs/developer-guide/zh/toolchain.md`
  - English: `seekdb-docs/developer-guide/en/toolchain.md`
  - Purpose: Install C++ compilation toolchain, OS compatibility, GLIBC version requirements

- **build-and-run.md** - Build and run
  - Chinese: `seekdb-docs/developer-guide/zh/build-and-run.md`
  - English: `seekdb-docs/developer-guide/en/build-and-run.md`
  - Purpose: Clone code, compile project (Debug/Release modes), run SeekDB instance

- **ide-settings.md** - IDE configuration
  - Chinese: `seekdb-docs/developer-guide/zh/ide-settings.md`
  - English: `seekdb-docs/developer-guide/en/ide-settings.md`
  - Purpose: Configure VSCode + ccls for code reading and development

### 1.3 Coding Standards (2 documents)

- **coding-convention.md** - Coding conventions
  - Chinese: `seekdb-docs/developer-guide/zh/coding-convention.md`
  - English: `seekdb-docs/developer-guide/en/coding-convention.md`
  - Purpose: SeekDB-specific coding habits and conventions (quick start)

- **coding-standard.md** - Coding standards
  - Chinese: `seekdb-docs/developer-guide/zh/coding-standard.md`
  - English: `seekdb-docs/developer-guide/en/coding-standard.md`
  - Purpose: Detailed C++ coding standards and constraints (in-depth reference)

### 1.4 Testing & Debugging (3 documents)

- **unittest.md** - Unit testing
  - Chinese: `seekdb-docs/developer-guide/zh/unittest.md`
  - English: `seekdb-docs/developer-guide/en/unittest.md`
  - Purpose: Write and run unit tests using Google Test

- **mysqltest.md** - MySQL testing
  - Chinese: `seekdb-docs/developer-guide/zh/mysqltest.md`
  - English: `seekdb-docs/developer-guide/en/mysqltest.md`
  - Purpose: Run mysqltest integration tests

- **debug.md** - Debugging
  - Chinese: `seekdb-docs/developer-guide/zh/debug.md`
  - English: `seekdb-docs/developer-guide/en/debug.md`
  - Purpose: Debug SeekDB using GDB, logs, and other tools

### 1.5 Core System Design (3 documents)

- **memory.md** - Memory management
  - Chinese: `seekdb-docs/developer-guide/zh/memory.md`
  - English: `seekdb-docs/developer-guide/en/memory.md`
  - Purpose: SeekDB memory management mechanism and multi-tenant memory isolation

- **logging.md** - Logging system
  - Chinese: `seekdb-docs/developer-guide/zh/logging.md`
  - English: `seekdb-docs/developer-guide/en/logging.md`
  - Purpose: Logging usage and implementation details

- **container.md** - Basic data structures
  - Chinese: `seekdb-docs/developer-guide/zh/container.md`
  - English: `seekdb-docs/developer-guide/en/container.md`
  - Purpose: Container classes provided by SeekDB (STL alternatives)

### 1.6 Contributing (1 document)

- **contributing.md** - Contributing code
  - Chinese: `seekdb-docs/developer-guide/zh/contributing.md`
  - English: `seekdb-docs/developer-guide/en/contributing.md`
  - Purpose: How to contribute code to SeekDB project

**Target Audience**: SeekDB contributors, core developers, system architects

---

## 2. User Guide - Python SDK

**Location**: `seekdb-docs/user-guide/zh/` (Chinese) and `seekdb-docs/user-guide/en/` (English)  
**Document Count**: 1 document × 2 languages = 2 documents  
**Overview**:
- Complete Python SDK (pyseekdb) API reference
- Simplified KV-style API for reduced learning curve
- Supports embedded, server, and OceanBase connection modes
- Provides Collection management, data operations, queries, and hybrid search

### 2.1 Python SDK API Reference

- **pyseekdb-sdk.md** - Python client API
  - Chinese: `seekdb-docs/user-guide/zh/pyseekdb-sdk.md`
  - English: `seekdb-docs/user-guide/en/pyseekdb-sdk.md`
  - Purpose: Complete Python SDK API documentation

**Document Content Structure**:

#### Background & Design Principles
- Simplified API design philosophy
- Schema-free data model
- Single Collection operation mode

#### Client Object
- **Embedded mode**: Local file storage
- **Server mode**: Connect to SeekDB server
- **OceanBase mode**: Connect to OceanBase database (with tenant support)

#### Collection Object
- **Data model**: Collection table structure
- **Management operations**:
  - `create_collection()` - Create collection
  - `get_collection()` - Get collection
  - `get_or_create_collection()` - Get or create collection
  - `delete_collection()` - Delete collection

#### Data Modification Operations
- **add()** - Add documents (auto-generate embeddings)
- **update()** - Update records
- **upsert()** - Insert or update
- **delete()** - Delete records (supports conditional deletion)

#### Query Operations
- **Vector similarity query**:
  - `query()` - Query using query_texts or query_embeddings
  - Supports n_results parameter to control return count
- **Query by ID**:
  - `get()` - Get records by ID
  - Supports limit and offset pagination
- **Hybrid search**:
  - `hybrid_search()` - Combine full-text search and vector search
  - Supports multi-recall and reranking (RRF)

#### Filter Conditions
- **where** - Metadata filtering:
  - Comparison operators: `$eq`, `$lt`, `$gt`, `$lte`, `$gte`, `$ne`, `$in`, `$nin`
  - Logical operators: `$or`, `$and`, `$not`
- **where_document** - Document content filtering:
  - `$contains` - Full-text index search
  - `$regex` - Regular expression matching
  - Logical operators: `$or`, `$and`

#### Return Field Control
- **include** parameter: Specify return fields (documents, metadatas, embeddings, distances)

#### Database Object
- `create_database()` - Create database
- `get_database()` - Get database
- `delete_database()` - Delete database
- `list_databases()` - List all databases

#### Example Code
- Complete usage examples
- Full workflow from creating Client to querying

**Target Audience**: Python developers, AI application developers, vector database users

---

## Language Support

All documentation available in bilingual versions:
- **Chinese**: Located in `zh/` directory
- **English**: Located in `en/` directory

## Quick Lookup Guide

### Learning SeekDB Development
→ See **Developer Guide** (Section 1)
- Start with environment setup: toolchain.md → build-and-run.md → ide-settings.md
- Learn coding standards: coding-convention.md → coding-standard.md
- Master testing & debugging: unittest.md → mysqltest.md → debug.md
- Dive into core systems: memory.md → logging.md → container.md

### Using Python SDK for Applications
→ See **User Guide - Python SDK** (Section 2)
- Read directly: pyseekdb-sdk.md
- Contains complete API reference and example code

### Understanding Specific Features
- **Connect to database**: pyseekdb-sdk.md → Client Object
- **Manage collections**: pyseekdb-sdk.md → Collection Object → Management Operations
- **Add data**: pyseekdb-sdk.md → Data Modification Operations → add()
- **Query data**: pyseekdb-sdk.md → Query Operations
- **Hybrid search**: pyseekdb-sdk.md → Query Operations → Hybrid Search
- **Filter conditions**: pyseekdb-sdk.md → Filter Conditions

---

**Total Documents**: 26 documents (12 developer guide docs × 2 languages + 1 user guide doc × 2 languages)

**Last Updated**: 2026-01-20
