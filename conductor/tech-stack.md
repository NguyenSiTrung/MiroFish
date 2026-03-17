# Tech Stack: MiroFish

## Architecture

- **Type**: Monorepo (frontend + backend)
- **Pattern**: Client-server with REST API
- **License**: AGPL-3.0

## Frontend

| Technology | Version | Purpose |
|-----------|---------|---------|
| Vue.js | 3.x | UI framework |
| Vite | 7.x | Build tool and dev server |
| Vue Router | 4.x | Client-side routing |
| D3.js | 7.x | Data visualization (agent networks, simulation graphs) |
| Axios | 1.x | HTTP client for API communication |

## Backend

| Technology | Version | Purpose |
|-----------|---------|---------|
| Python | >=3.11, <=3.12 | Runtime |
| Flask | 3.x | Web framework / REST API |
| OpenAI SDK | 1.x | LLM API integration (supports any OpenAI-compatible API) |
| Zep Cloud | 3.13.0 | Agent long-term memory |
| CAMEL-OASIS | 0.2.5 | Multi-agent social simulation engine |
| CAMEL-AI | 0.2.78 | AI agent framework |
| PyMuPDF | 1.24+ | PDF/document processing |
| Pydantic | 2.x | Data validation |
| python-dotenv | 1.x | Environment variable management |

## Package Management

| Tool | Scope |
|------|-------|
| npm | Root project + frontend dependencies |
| uv | Backend Python dependencies |

## Deployment

| Tool | Purpose |
|------|---------|
| Docker | Containerization |
| Docker Compose | Multi-service orchestration (frontend:3000, backend:5001) |

## Testing

| Tool | Scope |
|------|-------|
| pytest | Backend unit/integration tests |
| pytest-asyncio | Async test support |

## External Services

| Service | Purpose |
|---------|---------|
| LLM API (OpenAI-compatible) | Agent intelligence, content generation, analysis |
| Zep Cloud | Agent persistent memory storage |
