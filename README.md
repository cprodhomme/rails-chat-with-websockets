# Test Rails chat with websockets

## Build

```console
docker run --name rails-chat-tutorial-web \
            -e DATABASE_HOST=172.17.0.1 \
            -e DATABASE_PORT=5432 \
            -e DATABASE_USERNAME=postgres \
            -e DATABASE_PASSWORD=postgres \
            -e REDIS_URL=redis://172.17.0.1:6379/1 \
            -p 3000:3000 \
            rails-chat-tutorial
```

### Creating the PostgreSQL container

```console
docker run --name rails-chat-tutorial-pg
       -e POSTGRES_USER=postgres
       -e POSTGRES_PASSWORD=postgres
       -p 5432:5432
       -d postgres
```

### Creating the Redis container

```console
docker run --name rails-chat-tutorial-redis \
       -p 6379:6379 \
       -d redis
```