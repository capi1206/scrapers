The repository is organized into a modular structure to separate scraping logic, API services, database integration, and infrastructure:

- **`scrapers/`**  
  Contains the scraping modules for different medical directories.  
  - `base_scraper.py`: shared scraper functionality  
  - `<site>_scraper.py`: individual scraper implementations  

- **`api/`**  
  Houses the FastAPI service for exposing scraped data.  
  - `main.py`: starts the FastAPI application  
  - `routes/`: route definitions (`doctors.py`, `status.py`)  
  - `models/`: Pydantic models for API & DB (`doctor.py`, `base.py`)  
  - `db.py`: SQLAlchemy database connection  

- **`tests/`**  
  Holds unit and integration tests.  
  - `test_scrapers.py`: tests scraping functions  
  - `test_api.py`: tests API endpoints with TestClient  
  - `test_db.py`: integration tests with test DB  

- **`docker/`**  
  Dockerfiles for container builds.  
  - `Dockerfile.api`: API service image  
  - `Dockerfile.scraper`: scraper service image  

- **`scripts/`**  
  Utility scripts for orchestration.  
  - `run_scraper.py`: runs scrapers and pushes results to DB  

- **Top-level files:**  
  - `requirements.txt`: Python dependencies  
  - `pyproject.toml`: alternative dependency management (Poetry)  
  - `docker-compose.yml`: local dev environment (MySQL + API + scrapers)  
  - `.github/workflows/ci.yml`: GitHub Actions CI/CD pipeline  
  - `.flake8`: linting configuration  
  - `openapi.yaml`: OpenAPI/Swagger documentation  
  - `README.md`: project documentation 
