he repository is organized into a modular structure to separate scraping logic, API services, database integration, and infrastructure:

scrapers/
Contains the scraping modules for different medical directories. Each scraper is implemented in its own file, with a common base_scraper.py defining shared functionality.

api/
Houses the FastAPI service for exposing scraped data.

main.py starts the FastAPI application.

routes/ contains route definitions (e.g., doctors.py, status.py).

models/ contains Pydantic models used for request/response schemas and database mappings (doctor.py, base.py).

db.py defines the SQLAlchemy database connection layer.

tests/
Holds unit and integration tests.

test_scrapers.py validates scraping functions.

test_api.py tests API endpoints with FastAPI’s TestClient.

test_db.py checks integration with a test database.

docker/
Includes Dockerfiles for building container images:

Dockerfile.api for the API service.

Dockerfile.scraper for the scraper services.

scripts/
Utility scripts for orchestration, such as run_scraper.py, which runs scrapers and writes results into the database.

Top-level project files:

requirements.txt lists dependencies (or pyproject.toml if using Poetry).

docker-compose.yml spins up local services (MySQL, API, scrapers).

.github/workflows/ci.yml defines CI/CD pipelines (linting, tests).

.flake8 holds linting configuration.

openapi.yaml documents the API schema (OpenAPI/Swagger).

README.md explains setup, usage, and deployment instructions.
