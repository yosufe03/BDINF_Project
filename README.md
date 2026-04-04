# BDINF Final Project – Weather vs Renewable Energy

This project investigates how weather conditions affect renewable energy production in Germany.

## Included files
- `notebooks/Weather_Energy_Project.ipynb` – main notebook
- `docker-compose.yml` – starts MongoDB, mongo-express and JupyterLab
- `Dockerfile` – Python/Jupyter image for the notebook environment
- `.env.example` – example environment variables
- `requirements.txt` – Python dependencies
- `mongo-init/init.js` – optional MongoDB init script

## Quick start

1. Copy environment file:
   ```bash
   cp .env.example .env
   ```

2. Start the stack:
   ```bash
   docker compose up --build
   ```

3. Open:
   - JupyterLab: http://localhost:8888
   - mongo-express: http://localhost:8081

4. Open the notebook:
   - `notebooks/Weather_Energy_Project.ipynb`

## Notes
- The notebook is written so you can run it step by step.
- It uses:
  - Open-Meteo Historical Weather API
  - Energy-Charts API
  - MongoDB for NoSQL storage
- The MapReduce-style calculation is implemented in Python and a MongoDB aggregation example is also included.

## Suggested team workflow
- One person verifies API calls
- One person manages Docker/MongoDB
- One person works on the notebook analysis/visualization
- One person prepares presentation/architecture diagram
