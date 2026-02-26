---
name: create-fastapi-rest-api
description: Create a basic REST API using FastAPI with automatic documentation and validation
version: 1.0.0
metadata:
  skill_forge:
    domain: "fastapi"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [fastapi, python, api, rest, web-development]
    category: web-development
---

# Create FastAPI REST API

## When to Use
When you need to build a modern, high-performance REST API in Python with automatic documentation, data validation, and type hints.

## Prerequisites
- Python 3.8 or higher installed
- pip package manager
- Basic understanding of Python and HTTP concepts

## Procedure
1. Create project directory: `mkdir fastapi-project && cd fastapi-project`
2. Create virtual environment: `python -m venv venv`
3. Activate virtual environment: `source venv/bin/activate` (Linux/Mac) or `venv\Scripts\activate` (Windows)
4. Install FastAPI and Uvicorn: `pip install "fastapi[all]" uvicorn`
5. Create main.py file: `touch main.py`
6. Add basic API code to main.py:
   from fastapi import FastAPI
   from pydantic import BaseModel

   app = FastAPI()

   class Item(BaseModel):
       name: str
       price: float

   @app.get("/")
   def read_root():
       return {"Hello": "World"}

   @app.get("/items/{item_id}")
   def read_item(item_id: int, q: str = None):
       return {"item_id": item_id, "q": q}

   @app.post("/items/")
   def create_item(item: Item):
       return item
   ```
7. Run the development server: `uvicorn main:app --reload`
8. Access API documentation at: `http://127.0.0.1:8000/docs`

## Verification
- Server starts without errors and shows "Uvicorn running on http://127.0.0.1:8000"
- Browser shows "Hello World" at http://127.0.0.1:8000
- Interactive API docs load at http://127.0.0.1:8000/docs
- Test endpoints return expected JSON responses

## Pitfalls
- Virtual environment not activated leading to global package installation
- Port 8000 already in use (use `--port 8001` flag)
- Missing type hints break automatic validation
- Forgetting `--reload` flag requires manual server restarts during development

## Sources
- https://fastapi.tiangolo.com/
- https://github.com/fastapi
- https://realpython.com/get-started-with-fastapi/
- https://www.youtube.com/watch?v=7AMjmCTumuo
- https://en.wikipedia.org/wiki/FastAPI
```