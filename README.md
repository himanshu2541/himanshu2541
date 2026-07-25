# Himanshu

Final year undergrad at IIT Kharagpur. Mostly backend and infra - API design, data pipelines, deployment - with GenAI/RAG work on the side.

[LinkedIn](https://linkedin.com/in/himanshu2541) · [Email](mailto:s.himanshu.2541@gmail.com)

---

## Currently building

### NyayOps - Legal-Ops SaaS Platform
Multi-tenant case management platform for legal teams - workflow automation, live eCourts data integration, hearing tracking, admin console. Split across independently-versioned services that talk over HTTP.

**Backend** (FastAPI, PostgreSQL, SQLAlchemy, Celery, Redis, S3) - multi-tenant API, case workflow engine, RBAC, document storage, hearing reminders.

**Court Data Service (CDE)** - an in-house eCourts scraper built to replace a paid vendor. Uses BeautifulSoup and pdfplumber for extraction, unsupervised clustering (CSF) for grouping unstructured court data, supervised models for classification on top of that, and an LLM fallback for cases the models aren't confident on.

**Deployment/Infra** - backend services containerized with Docker and deployed on AWS EC2; handling the environment setup, process management, and service-to-service networking myself rather than relying on a managed PaaS.

Frontend and mobile clients (React/TypeScript dashboard, Flutter mobile app) exist to consume this backend - built by me as well, but secondary to the service layer.

### JeevanHub - Ayurvedic Healthcare Platform
Fixed Issues with Doctor consultations, medicine e-commerce, diet/yoga plans, and AI chatbot.

Backend/data work: fuzzy medicine search (Fuse.js) with server-side pagination, Razorpay checkout with prescription-gated ordering, retailer bulk upload via CSV/XLSX, an AI chatbot (Sanjeevani, Groq-based) grounded in real product data instead of freeform generation, and a data-leakage bug fix in the dosha/prakriti recommendation logic. Also did a full frontend migration off CRA onto Vite and Tailwind when the old stack became a bottleneck, and fixed a route-splitting issue that had bloated the bundle size.

---

## Earlier projects

### Policy Assistant - GraphRAG for policy/legal Q&A
A retrieval-augmented chatbot for answering complex policy and legal queries. Instead of plain vector search, it uses Neo4j to model relationships between clauses, sections, and precedents, so multi-hop questions ("which sub-clause overrides this one under condition X") resolve correctly instead of just returning the nearest text chunk. Runs on Mistral-7B.

### NLP-to-SQL Engine
A tool that converts natural language questions into executable SQL against a PostgreSQL schema, using LangChain to manage schema-aware prompting and query validation before execution - built to let non-technical users query structured data without writing SQL themselves.

### Git Sentinel
Repo monitoring tool for CI/CD - automated checks for common security/config issues on each push.

---

## Also spend time on

- **System design** - service decomposition, caching strategy, queue-based async workflows (Celery/Redis, arq), designing for multi-tenancy
- **Design patterns** - creational (builder, factory), behavioral (strategy, observer) - applied where they solve a real problem, not for their own sake
- **SOLID principles** and clean architecture, mainly in Python codebases

---

## Stack

**Backend/Data:** Python, FastAPI, PostgreSQL, SQLAlchemy, Celery, Redis, arq
**DevOps/Cloud:** Docker, AWS (EC2, S3), Azure
**GenAI:** LangChain, Groq, Mistral, RAG/GraphRAG, PyTorch
**Frontend (secondary):** TypeScript, React, Flutter
