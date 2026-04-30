# docker-node-demo

A minimal Node.js + Express app containerised with Docker. Built to learn and demonstrate the basics of Docker — writing a Dockerfile, using Docker Compose, and running a Node app in an isolated container.

---

## What It Does

Starts an Express server inside a Docker container that responds to HTTP requests. Simple by design — the focus is on the Docker setup, not the app itself.

---

## Stack

- **Node.js 20** (Alpine base image)
- **Express** — single route HTTP server
- **Docker** — containerisation
- **Docker Compose** — local dev with volume mounting

---

## Project Structure

```
├── app.js              Express server
├── Dockerfile          Container build instructions
├── docker-compose.yml  Local dev setup with hot reload
└── package.json
```

---

## Getting Started

**With Docker Compose (recommended):**
```bash
docker-compose up
```
Starts the app on `http://localhost:3000` with the source directory mounted as a volume.

**With Docker directly:**
```bash
docker build -t docker-node-demo .
docker run -p 3000:3000 docker-node-demo
```

**Without Docker:**
```bash
npm install
node app.js
```

---

## What I Learned

- Writing a `Dockerfile` from scratch — base image, `WORKDIR`, `COPY`, `RUN`, `EXPOSE`, `CMD`
- Using `.dockerignore` to keep images lean
- Docker Compose for local development with volume mounts so code changes reflect without rebuilding
- Port mapping between container and host
- The difference between `RUN` (build time) and `CMD` (runtime)

---

## License

MIT
