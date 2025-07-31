# iX Construct

iX Construct is a platform for managing and automating financial workflows in the construction industry. It enables secure fund management, optimized material procurement, verified worker payments, and bank-compliant reporting. Designed for use in emerging markets where construction is largely informal, the platform bridges the gap between capital, labor, and logistics.

## Overview

iX Construct offers:

- Escrow-style fund control for construction clients and banks
- Automated disbursement to workers and suppliers
- AI-driven optimization of bills of quantities (BoQs)
- Real-time materials pricing comparison from manufacturers
- Architectural plan analysis for design efficiency
- Worker verification and financial inclusion services
- Bank integration for mortgage and construction loan oversight
- Order logistics and delivery tracking for materials

This repository contains the core backend services (written in Haskell), frontend interface (JavaScript), and supporting tools (Ruby for automation and scripting).

---

## System Architecture

### Core Components

| Component | Language | Description |
|----------|----------|-------------|
| `backend/` | Haskell | Business logic, payment automation, approval flows, BoQ parsing |
| `frontend/` | JavaScript | Admin dashboard, client portal, manufacturer & worker interfaces |
| `scripts/` | Ruby | Data import/export, migration tools, integration scripts |
| `db/` | SQL (PostgreSQL) | Core relational schema: users, projects, transactions |
| `boqx/` | Haskell | BoQ analysis and optimization engine |
| `ai-plans/` | TBD | Architectural plan evaluation (AI/ML pipeline) |
| `infra/` | YAML/Terraform | Cloud infrastructure definitions and deployment files |

---

## Key Features

### Fund Management & Disbursement

- Client deposits funds into platform-managed virtual account
- Approval workflows per payment (client, foreman, PM)
- Automated release of funds to verified workers and suppliers

### BoQ Optimization

- Upload of standard BoQ format (CSV, XLSX, JSON)
- Real-time pricing from manufacturer catalogues
- Suggestions for cost-saving materials or quantities

### Worker Registry

- National ID + skill verification system
- Matchmaking for job opportunities
- Retirement savings and optional health fund contribution from wages

### Bank & Lender API Integration

- Construction loan application assist tools
- API access for banks to monitor project spend and milestone progress

---

## Technologies Used

| Area | Tech |
|------|------|
| Backend | Haskell (Servant, Persistent, STM) |
| Frontend | JavaScript (React or Svelte) |
| Scripting | Ruby (Rake, Sinatra for CLI APIs) |
| Database | PostgreSQL, Redis, CouchDB |
| Infrastructure | Docker, Kubernetes, NGINX, Terraform |
| Verification | TLA+ (for payment workflows) |

---

## Getting Started

### Prerequisites

- GHC (Haskell compiler)
- Node.js
- Ruby (>= 3.1)
- PostgreSQL
- Docker & Docker Compose
- Redis server (local or hosted)

### Installation (Development)

```bash
git clone https://github.com/ix-technologies/ix-construct.git
cd ix-construct

# Start backend
cd backend
stack build
stack exec ix-backend

# Start frontend
cd ../frontend
npm install
npm run dev

# Start supporting services
docker-compose up redis postgres
