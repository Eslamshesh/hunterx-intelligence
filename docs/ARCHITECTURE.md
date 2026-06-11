# System Architecture - HunterX Intelligence

## High-Level Architecture

```
Frontend (Next.js) → API Gateway (NestJS) → Services
  ↓
PostgreSQL + Elasticsearch + Redis
  ↓
Background Processing (Scrapers, AI, Notifications)
```

## Core Components

1. **Frontend**: Next.js 14, TypeScript, Tailwind, shadcn/ui
2. **Backend**: NestJS, TypeORM, PostgreSQL
3. **Search**: Elasticsearch for full-text search
4. **Cache**: Redis + BullMQ for queues
5. **AI**: OpenAI/Claude integration
6. **Scrapers**: Playwright + RSS parsers

## Data Flow

1. Scrapers fetch from 30+ sources
2. AI classification engine processes content
3. Data indexed in PostgreSQL + Elasticsearch
4. Notifications sent to subscribed researchers
5. Knowledge graph updated with relationships
