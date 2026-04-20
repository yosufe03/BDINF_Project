# BDINF Final Project – Weather vs Renewable Energy

This project investigates how weather conditions affect renewable energy production in Austria, with a focus on solar and wind generation.

## Project goal

We combine two API-based data sources and analyze whether weather variables such as shortwave radiation and wind speed are related to renewable electricity production.

## Data sources

- Open-Meteo Historical Weather API
- Energy-Charts public power API

## Tech stack

- Jupyter Notebook for the project workflow and documentation
- Python with pandas, requests, matplotlib and pymongo
- MongoDB as NoSQL database for raw and processed data
- Docker Compose for a reproducible local environment

## Project structure

- `anaconda_projects/main.ipynb` – main notebook
- `anaconda_projects/data/raw/` – cached raw API responses
- `anaconda_projects/data/processed/` – cleaned and merged CSV outputs
- `docker-compose.yml` – starts MongoDB, mongo-express and JupyterLab
- `Dockerfile` – Python/Jupyter image used by the `jupyter` service
- `.env.example` – example environment variables
- `requirements.txt` – Python dependencies

## Quick start

1. Create a local environment file:
   ```bash
   cp .env.example .env
   ```
2. Start the full stack:
   ```bash
   docker compose up --build
   ```
3. Open the tools:
   - JupyterLab: http://localhost:8888
   - mongo-express: http://localhost:8081
4. Open the notebook:
   - `anaconda_projects/main.ipynb`

## MongoDB usage

The notebook stores data in MongoDB collections such as:

- `weather_raw`
- `energy_raw`
- `merged_hourly`
- `analysis_results`

This helps us cover the NoSQL/database requirement of the project and keep raw plus processed data separated.

## Notes

- The notebook is written so it can be executed step by step.
- Environment variables are loaded from `.env` when available.
- The project includes a MapReduce-style calculation in Python and an example MongoDB aggregation pipeline.

## Suggested team workflow

- One person verifies API calls and data quality
- One person manages Docker and MongoDB
- One person works on analysis and visualizations
- One person prepares conclusions and the architecture diagram
