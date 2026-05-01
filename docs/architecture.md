                ┌──────────────┐
                │  Frontend    │ (React)
                └──────┬───────┘
                       │
                       ▼
                ┌──────────────┐
                │   FastAPI    │ (Backend)
                └──────┬───────┘
                       │
     ┌─────────────────┼─────────────────┐
     ▼                 ▼                 ▼
 PostgreSQL        Redis Cache        AI Service
 (Primary DB)      (Query Cache)      (Ollama)

---------------- FUTURE (Optional) ----------------

Ingestion API → Kafka → Consumers → PostgreSQL

Airflow DAGs ───────────────→ PostgreSQL