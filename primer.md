# IRFAssist – Product Primer

## 🎯 Purpose

IRFAssist is an **AI-powered automation assistant for small CPA firms**, helping firms with:

- **Intake** of client documents
- **Review** and classification of financial/tax documents
- **Finalization** of accounting/tax data

The product is fully **turnkey** — it includes pre-configured hardware, pre-installed software, and an intelligent assistant powered by a local Mistral LLM via Ollama.

---

## 🧩 Architecture Overview

### 🖥️ Hardware
- Base system: 4TB internal SSD
- External USB 3.0 SSD (12TB) for archive/document storage
- Ubuntu Desktop with GUI pre-installed

### 🧠 AI Engine
- Local model: `mistral:7b` via Ollama
- Assistant runs inside VS Code (Continue.dev) for development
- All prompts use a verified system message to:
  - Enforce production-grade coding
  - Prefer `polars` over `pandas`
  - Use the latest Python patterns
  - Reason thoroughly before output

---

## 🧱 Modules

| Module Group        | Subcomponents |
|---------------------|---------------|
| **Core Assistant**  | IRFA Intake, Review, Finalization |
| **Firm Workbench**  | CRM-lite interface, Client records, Billing info |
| **MCP Orchestration** | MCP for File Intake, NLP Parsing, AI Helpdesk, Admin Dashboard |
| **MTJ Admin**       | Hidden module for master control (non-client accessible) |
| **AI Features**     | OCR, classification, vector search, doc parsing, summarization |

---

## 🗃️ Databases

| Purpose                | DB Used      | Notes |
|------------------------|--------------|-------|
| System Configuration   | SQLite       | Encrypted at rest |
| Firm + Client CRM Data | PostgreSQL   | Multi-tenant, isolated schemas |
| Vector Storage         | Chroma DB    | For AI document search |
| Regulatory Corpus      | DuckDB       | Used for lookups & classification |
| Logs / Audit Trail     | PostgreSQL   | Append-only log structure |

---

## 🔐 Security Requirements

- All data encrypted at rest and in transit
- Zero cross-tenant access risk
- Local-only operation (no cloud LLM use)
- Self-contained environment
- USB-based software updates
- Admin-only read access via MTJ Admin

---

## 💼 Pricing & Deployment

- Product is licensed **per active client**, not per user
- All tiers include full feature set; only client count varies
- Delivered hardware includes:
  - Fully configured Ubuntu GUI system
  - All databases initialized
  - LLM already installed and verified

---

## 💻 Development Setup

- Python 3.13.4 (via Brew)
- VS Code with Continue.dev and GitHub integration
- `.venv` named `.irfassist`
- Requirements file in project root
- Using `Continue.dev` for local agent support via `mistral:7b`

---

## ✅ Current Status

- Hardware options scoped and priced
- Architecture finalized (4 MCP servers)
- IRFAssist dev environment initialized
- Mistral via Ollama fully configured
- Project repo synced with GitHub