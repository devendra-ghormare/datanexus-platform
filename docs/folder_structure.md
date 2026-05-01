datanexus/
│
├── backend/                  # FastAPI core app
│   ├── api/                  # Route layer (thin controllers)
│   │   ├── v1/
│   │   │   ├── ingest.py
│   │   │   ├── query.py
│   │   │   ├── ai.py
│   │   │   └── datasets.py
│   │
│   ├── core/                 # App config & shared logic
│   │   ├── config.py
│   │   ├── security.py
│   │   ├── logging.py
│   │   └── database.py
│   │
│   ├── models/               # ORM models (PostgreSQL)
│   │   ├── user.py
│   │   ├── dataset.py
│   │   ├── table.py
│   │   ├── query.py
│   │   └── job.py
│   │
│   ├── schemas/              # Pydantic schemas
│   │   ├── user.py
│   │   ├── dataset.py
│   │   ├── query.py
│   │   └── ai.py
│   │
│   ├── services/             # Business logic (IMPORTANT layer)
│   │   ├── ingestion_service.py
│   │   ├── query_service.py
│   │   ├── ai_service.py
│   │   ├── cache_service.py
│   │   └── dataset_service.py
│   │
│   ├── repositories/         # DB access abstraction
│   │   ├── user_repo.py
│   │   ├── dataset_repo.py
│   │   ├── query_repo.py
│   │   └── job_repo.py
│   │
│   ├── ai/                   # AI-specific logic (keep isolated)
│   │   ├── llm_client.py     # Ollama wrapper
│   │   ├── prompt_builder.py
│   │   ├── sql_generator.py
│   │   └── validator.py      # SQL safety checks
│   │
│   ├── utils/                # Helpers
│   │   ├── parsers.py
│   │   ├── file_handler.py
│   │   └── time.py
│   │
│   └── main.py               # FastAPI entry point
│
│
├── workers/                  # Kafka consumers
│   ├── consumers/
│   │   ├── ingestion_consumer.py
│   │   └── event_processor.py
│   │
│   ├── services/             # Worker-specific logic
│   │   └── processing_service.py
│   │
│   └── main.py
│
│
├── airflow/                  # Batch processing
│   ├── dags/
│   │   ├── ingestion_dag.py
│   │   ├── transformation_dag.py
│   │   └── cleanup_dag.py
│   │
│   ├── plugins/
│   └── config/
│
│
├── frontend/                 # React app
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   │   ├── QueryPage.jsx
│   │   │   └── DatasetPage.jsx
│   │   ├── services/         # API calls
│   │   ├── hooks/
│   │   └── utils/
│   │
│   └── public/
│
│
├── infrastructure/           # DevOps layer
│   ├── docker/
│   │   ├── backend.Dockerfile
│   │   ├── frontend.Dockerfile
│   │   ├── worker.Dockerfile
│   │   └── airflow.Dockerfile
│   │
│   ├── docker-compose.yml
│   └── env/
│       └── .env
│
│
├── scripts/                  # Utility scripts
│   ├── seed_db.py
│   ├── create_dataset.py
│   └── run_migrations.sh
│
│
├── tests/                    # Testing
│   ├── unit/
│   ├── api/
│   └── integration/
│
│
├── docs/                     # Documentation
│   ├── architecture.md
│   ├── api.md
│   └── setup.md
│
│
└── README.md