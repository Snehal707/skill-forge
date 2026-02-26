---
name: redis-setup-local
description: Install and configure Redis for local development and basic operations
version: 1.0.0
metadata:
  skill_forge:
    domain: "redis"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [redis, database, cache, memory, key-value]
    category: database
---

# Redis Local Setup and Basic Operations

## When to Use
- Need an in-memory key-value store for caching
- Building applications requiring fast data access
- Implementing session storage or message queuing
- Prototyping real-time applications with sub-millisecond latency

## Prerequisites
- Linux/macOS system or Windows with WSL
- sudo/admin privileges for installation
- Basic command line familiarity

## Procedure
1. Install Redis server: `sudo apt update && sudo apt install redis-server` (Ubuntu/Debian) or `brew install redis` (macOS)
2. Start Redis service: `sudo systemctl start redis-server` (Linux) or `brew services start redis` (macOS)
3. Enable auto-start: `sudo systemctl enable redis-server` (Linux only)
4. Connect to Redis CLI: `redis-cli`
5. Test basic operations:
   - Set a key: `SET mykey "Hello Redis"`
   - Get a key: `GET mykey`
   - Set with expiration: `SETEX tempkey 10 "expires in 10 seconds"`
   - Check if key exists: `EXISTS mykey`
6. Configure persistence (optional): Edit `/etc/redis/redis.conf` and set `save 900 1` for snapshots
7. Restart service if config changed: `sudo systemctl restart redis-server`

## Verification
- Check service status: `sudo systemctl status redis-server`
- Ping Redis: `redis-cli ping` should return "PONG"
- Monitor operations: `redis-cli monitor`
- Check memory usage: `redis-cli info memory`

## Pitfalls
- Redis runs in-memory by default - data lost on restart without persistence
- Default configuration accepts connections from localhost only
- No authentication enabled by default - secure before production use
- Memory usage can grow unbounded without proper key expiration policies

## Sources
- https://redis.io/
- https://github.com/redis/redis
- https://en.wikipedia.org/wiki/Redis
- https://app.redislabs.com/
- https://www.youtube.com/watch?v=z_NbVtbgBJw