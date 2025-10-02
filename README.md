# My n8n local setup

## Setup

Create Project Directory

```sh
# Create dedicated directory for n8n data persistence
mkdir -p ~/n8n-local
cd ~/n8n-local

# Create subdirectory for persistent data
mkdir -p .n8n
```

Pull and run n8n container

```sh
# Pull latest n8n image (one-time, ~500MB download)
docker pull n8nio/n8n

# Run n8n container with proper configuration
docker run -d \
  --name n8n \
  -p 5678:5678 \
  -v ~/n8n-local/.n8n:/home/node/.n8n \
  -e N8N_SECURE_COOKIE=false \
  -e GENERIC_TIMEZONE="America/Los_Angeles" \
  -e TZ="America/Los_Angeles" \
  n8nio/n8n
```

open http://localhost:5678

## Getting started

- sign up (doesn't need to be actual email)
- go nuts!
