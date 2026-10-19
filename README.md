# PM Job Matcher MVP

A PM-first job discovery, deduplication, matching, and resume-tailoring prototype.

## What this scaffold includes

- FastAPI backend
- Job normalization schema
- Deduplication service
- PM subclassification service
- Resume/profile matching service
- Opportunity ranking
- Generic Next.js frontend dashboard
- Mock job and candidate data for local development

## Architecture

```text
Job sources
   -> normalize
   -> deduplicate
   -> hard filters
   -> PM classification
   -> evidence-based matching
   -> opportunity ranking
   -> resume tailoring queue
```

## Run locally

### Backend

```bash
cd backend
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\\Scripts\\activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```

Open: http://localhost:8000/docs

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Open: http://localhost:3000

The frontend expects the API at `http://localhost:8000` by default.

## Next build steps

1. Add PostgreSQL + pgvector persistence.
2. Add source adapters for company ATS feeds and VC job boards.
3. Add canonical job identity + source provenance.
4. Replace heuristic PM classification with structured LLM output.
5. Add resume parsing into an evidence graph.
6. Add qualification extraction and evidence matching.
7. Add DOCX/PDF resume compilation.
8. Add scheduled ingestion and freshness checks.

