```markdown
---
name: redis-setup-and-basic-operations
description: Install and configure Redis server locally, then perform basic key-value operations and verification.
metadata:
  skill_forge:
    domain: "redis"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
    version: "1.0.0"
  hermes:
    tags:
      - redis
      - database
      - cache
      - key-value
      - memory
    category: database
---

# Redis Setup and Basic Operations

## When to Use
When you need to set up a fast in-memory data store for caching, session storage, real-time analytics, or as a message broker.

## Prerequisites
- Operating system: Linux, macOS, or Windows with WSL
- Administrative privileges for installation
- Basic command line familiarity

## Procedure
1. Install Redis server: `sudo apt-get update && sudo apt-get install redis-server` (Ubuntu/Debian)
2. Start Redis service: `sudo systemctl start redis-server`
3. Enable auto-start: `sudo systemctl enable redis-server`
4. Connect to Redis CLI: `redis-cli`
5. Test basic operations:
   - Set a key: `SET mykey "Hello Redis"`
   - Get a key: `GET mykey`
   - Set with expiration: `SETEX tempkey 60 "expires in 60 seconds"`
   - Check if key exists: `EXISTS mykey`
6. Test data structures:
   - Create a list: `LPUSH mylist "item1" "item2" "item3"`
   - Get list items: `LRANGE mylist 0 -1`
   - Create a hash: `HSET user:1 name "John" age "30"`
   - Get hash field: `HGET user:1 name`
7. Exit Redis CLI: `EXIT`

## Verification
- Check Redis is running: `sudo systemctl status redis-server`
- Test connection: `redis-cli ping` (should return "PONG")
- Monitor Redis: `redis-cli monitor` (shows real-time commands)
- Check memory usage: `redis-cli info memory`

## Pitfalls
- Redis runs in memory - data is lost on restart unless persistence is configured
- Default configuration allows connections from localhost only
- No authentication by default - secure before production use
- Memory usage grows with data size - monitor and set limits
- Port 6379 should be firewalled in production environments

## Sources
- https://redis.io/
- https://github.com/redis/redis
- https://en.wikipedia.org/wiki/Redis
- https://app.redislabs.com/
- https://www.youtube.com/watch?v=z_NbVtbgBJw
```