# HunterX Intelligence

**Production-Grade Security Intelligence Platform**

A modern platform that automatically aggregates, classifies, ranks, and displays the latest Web2 and Web3 vulnerability writeups, bug bounty reports, security research articles, exploit analyses, and smart contract vulnerability disclosures.

## 🎯 Core Mission

Empower security researchers and elite bug hunters with real-time, AI-classified security intelligence from 50+ sources including:

- **Web2**: HackerOne, Bugcrowd, Intigriti, Project Zero, PortSwigger, GitHub Security Advisories
- **Web3**: Immunefi, Sherlock, Cantina, CodeHawks, Zellic, Halborn, OpenZeppelin

## 🚀 Features

### Core
1. **Vulnerability Search Engine** - Search by type, severity, date, source
2. **Live Writeups Aggregator** - Auto-fetch from 30+ sources
3. **AI Classification Engine** - Auto-extract vulnerability metadata
4. **Web3 Security Feed** - Dedicated smart contract audit dashboard
5. **Bug Hunter Feed** - Trending, newest, most severe writeups

### Advanced
6. **AI Knowledge Graph** - Relationship mapping between vulnerabilities
7. **Researcher Dashboard** - Bookmarks, watchlists, alerts
8. **Advanced Filtering** - Multi-criteria filtering
9. **Trending Analytics** - Charts and insights
10. **Modern UI** - Next.js + Tailwind + shadcn/ui

### Bonus
- Daily/Weekly Digests
- CVE Feed
- Telegram/Discord/Email Alerts
- Researcher Reputation System
- AI Recommendations

## 🏗️ Tech Stack

**Frontend**
- Next.js 14+ (App Router)
- TypeScript
- Tailwind CSS
- shadcn/ui
- TanStack Query
- Zustand (State)

**Backend**
- NestJS (TypeScript)
- PostgreSQL (Primary DB)
- Elasticsearch (Search)
- Redis + BullMQ (Queues)
- OpenAI/Claude (AI)

**Infrastructure**
- Docker & Docker Compose
- Kubernetes Ready
- GitHub Actions CI/CD

**Scraping & Integration**
- Playwright
- RSS Parsers
- Native APIs

## 📁 Project Structure

```
hunterx-intelligence/
├── backend/              # NestJS API
├── frontend/             # Next.js Dashboard
├── shared/               # Shared types
├── scrapers/             # Data collection
├── kubernetes/           # K8s configs
├── docker-compose.yml    # Local development
├── .github/workflows/    # CI/CD
└── docs/                 # Documentation
```

## 🔧 Quick Start

### Prerequisites
- Node.js 18+
- Docker & Docker Compose
- PostgreSQL 14+
- Redis 7+

### Development

```bash
# Clone and install
git clone https://github.com/Eslamshesh/hunterx-intelligence.git
cd hunterx-intelligence

# Start services (PostgreSQL, Redis, Elasticsearch)
docker-compose -f docker-compose.dev.yml up -d

# Backend setup
cd backend
npm install
cp .env.example .env
npm run typeorm migration:run
npm run start:dev

# Frontend setup (new terminal)
cd frontend
npm install
cp .env.example .env.local
npm run dev
```

Access:
- **Frontend**: http://localhost:3000
- **API**: http://localhost:3001
- **Elasticsearch**: http://localhost:9200
- **Redis**: localhost:6379

## 📊 Database Schema

See [SCHEMA.md](./docs/SCHEMA.md) for complete schema design.

Key tables:
- `vulnerabilities` - Indexed vulnerability data
- `articles` - Security articles/writeups
- `sources` - Data source configurations
- `tags` - Vulnerability classifications
- `researchers` - User profiles with reputation
- `bookmarks` - Saved articles
- `alerts` - User alert subscriptions

## 🤖 AI Classification Pipeline

1. **Fetch** - Scraper retrieves new content
2. **Parse** - Extract metadata and content
3. **Classify** - OpenAI/Claude auto-classifies
4. **Index** - Store in PostgreSQL + Elasticsearch
5. **Notify** - Alert subscribed researchers

## 🔐 Security

- JWT Authentication
- Rate Limiting
- CORS Configuration
- Environment-based secrets
- SQL Injection Prevention (TypeORM ORM)
- XSS Protection (React Safe)

## 📈 Scaling

- Elasticsearch for full-text search
- Redis caching layer
- BullMQ for async jobs
- PostgreSQL replication ready
- Kubernetes deployment configs
- Horizontal pod autoscaling

## 📚 Documentation

- [System Architecture](./docs/ARCHITECTURE.md)
- [API Documentation](./docs/API.md)
- [Database Schema](./docs/SCHEMA.md)
- [Deployment Guide](./docs/DEPLOYMENT.md)
- [Contributing](./CONTRIBUTING.md)

## 🎯 Vulnerability Types Supported

### Web2
IDOR, SSRF, XSS, SQLi, CSRF, Race Condition, Request Smuggling, GraphQL, OAuth, JWT, XXE, SSTI, Prototype Pollution, LFI/RFI, Access Control, Business Logic

### Web3
Reentrancy, Price Oracle Manipulation, Flash Loan, Signature Replay, Delegatecall Abuse, Access Control, MEV, Liquidation Bugs, Bridge Vulnerabilities, Upgradeability Issues, Governance Attacks, ERC20/4626 Issues, Account Abstraction

## 📝 License

MIT

## 🤝 Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md)

## 📞 Support

Open an issue on GitHub or contact security@hunterx.ai
