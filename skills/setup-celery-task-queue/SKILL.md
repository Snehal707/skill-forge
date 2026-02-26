---
name: setup-celery-task-queue
description: Set up and configure Celery distributed task queue for asynchronous job processing
version: 1.0.0
metadata:
  skill_forge:
    domain: "celery"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 1
  hermes:
    tags: [celery, distributed-systems, task-queue, python, async]
    category: backend
---

# Setup Celery Distributed Task Queue

## When to Use
When you need to process background tasks, handle long-running operations, or distribute work across multiple workers in a Python application.

## Prerequisites
- Python 3.7+ installed
- Redis or RabbitMQ message broker running
- pip package manager

## Procedure
1. Install Celery: `pip install celery[redis]`
2. Create celery app file `celery_app.py`:
   from celery import Celery
   
   app = Celery('tasks', broker='redis://localhost:6379/0')
   
   @app.task
   def add(x, y):
       return x + y
   ```
3. Start Redis broker: `redis-server`
4. Start Celery worker: `celery -A celery_app worker --loglevel=info`
5. Test task execution:
   ```python
   from celery_app import add
   result = add.delay(4, 4)
   print(result.get())
   ```

## Verification
- Worker logs show "ready" status
- Test task returns correct result (8)
- Redis connection successful in worker output

## Pitfalls
- Broker must be running before starting workers
- Task results expire by default, configure result backend for persistence
- Import paths must be consistent between worker and caller

## Sources
- https://docs.celeryq.dev/
```