medical-scrapers/                                                                                                                                                                            
│
├── scrapers/                   # individual scrapers                                                                                                                                        
│   ├── __init__.py
│   ├── base_scraper.py         # common scraper utilities (requests, retries, parsing)
│   ├── directory1_scraper.py   # your first scraper here
│   └── directory2_scraper.py   # next ones
│
├── api/                        # FastAPI service for Cloud Run
│   ├── __init__.py
│   ├── main.py                 # API entry point (FastAPI app)
│   ├── routers/                # endpoints grouped by logic
│   │   ├── __init__.py
│   │   ├── doctors.py
│   │   └── status.py
│   ├── models/                 # Pydantic models (schemas for API & DB)
│   │   ├── __init__.py
│   │   ├── doctor.py
│   │   └── base.py
│   └── db.py                   # MySQL connection layer (SQLAlchemy)
│
├── tests/
│   ├── __init__.py
│   ├── test_scrapers.py        # unit tests for scraper functions
│   ├── test_api.py             # tests API endpoints with TestClient
│   └── test_db.py              # integration test with test DB
│
├── docker/
│   ├── Dockerfile.api          # build for API service
│   └── Dockerfile.scraper      # build for scrapers
│
├── scripts/
│   └── run_scraper.py          # orchestrates scrapers, pushes to DB
│
│
├── requirements.txt
├── pyproject.toml              # if using poetry
├── docker-compose.yml          # for local dev (MySQL + API + scraper)
├── .github/workflows/ci.yml    # GitHub Actions for linting/tests
├── .flake8                     # linting config
├── openapi.yaml                # generated from FastAPI or hand-written
└── README.md
