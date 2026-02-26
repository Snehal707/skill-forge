```markdown
---
name: create-fastapi-application
description: Create a basic FastAPI web application with automatic API documentation and JSON endpoints.
metadata:
  skill_forge:
    domain: "fastapi"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
    version: "1.0.0"
  hermes:
    tags:
      - fastapi
      - python
      - web-api
      - rest
      - framework
    category: web-development
---

# Create FastAPI Application

## When to Use
When you need to build a high-performance Python web API with automatic documentation, data validation, and modern async support.

## Prerequisites
- Python 3.8 or higher installed
- pip package manager

## Procedure
1. Install FastAPI and Uvicorn: `pip install fastapi uvicorn[standard]`
2. Create a new file called `main.py`
3. Add basic FastAPI application code:
   ```python
   from fastapi import FastAPI
   
   app = FastAPI()
   
   @app.get("/")
   def read_root():
       return {"Hello": "World"}
   
   @app.get("/items/{item_id}")
   def read_item(item_id: int, q: str = None):
       return {"item_id": item_id, "q": q}
   ```
4. Run the application: `uvicorn main:app --reload`
5. Test the API at `http://127.0.0.1:8000`
6. View automatic documentation at `http://127.0.0.1:8000/docs`

## Verification
- Navigate to `http://127.0.0.1:8000` and see JSON response `{"Hello": "World"}`
- Check `http://127.0.0.1:8000/docs` shows interactive API documentation
- Test endpoint `http://127.0.0.1:8000/items/5?q=somequery` returns structured JSON

## Pitfalls
- Ensure Python 3.8+ is used (FastAPI requires modern Python features)
- Use `--reload` flag only in development (not production)
- Port 8000 must be available or specify different port with `--port 8080`
- Import errors may indicate missing dependencies - reinstall with `pip install fastapi[all]`

## Sources
- https://fastapi.tiangolo.com/
- https://github.com/fastapi/fastapi
- https://www.youtube.com/watch?v=7AMjmCTumuo
- https://en.wikipedia.org/wiki/FastAPI
- https://realpython.com/get-started-with-fastapi/
```