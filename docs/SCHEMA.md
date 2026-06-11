# Database Schema - HunterX Intelligence

## Core Tables

### users
- id (PK), email (UNIQUE), username (UNIQUE), password_hash, role, reputation_score, created_at, updated_at

### articles
- id (PK), title, url (UNIQUE), content, source_id (FK), severity, vulnerability_type, tags (JSONB), published_at, created_at

### sources
- id (PK), name (UNIQUE), url, type (api/rss/scraper), category (web2/web3), is_active

### tags
- id (PK), name (UNIQUE), category, color, usage_count, created_at

### alerts
- id (PK), user_id (FK), name, query (JSONB), notification_method, frequency, is_active, created_at

### bookmarks
- id (PK), user_id (FK), article_id (FK), created_at

### knowledge_graph_nodes
- id (PK), entity_type, entity_name, description, metadata (JSONB), created_at

### knowledge_graph_edges
- id (PK), source_node_id (FK), target_node_id (FK), relationship_type, strength (0-1), evidence_articles (JSONB)

## Indexing Strategy

- Full-text search on articles (title, content)
- Date range indexing on published_at
- Tag filtering (JSONB GIN index)
- Source filtering (indexed)
- Severity filtering (indexed)

## Elasticsearch Mappings

- Title: text analyzer
- Content: text analyzer
- Tags: keyword
- Severity: keyword
- Vulnerability_type: keyword
- Published_at: date
