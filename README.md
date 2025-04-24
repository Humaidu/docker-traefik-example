# 🌀 Docker + Traefik Example (Beginner Friendly)

This project demonstrates how to use [Traefik](https://traefik.io/) as a reverse proxy with Docker Compose to route traffic to multiple services running on the same machine.

You’ll learn how to:
- Set up Traefik as a reverse proxy
- Route multiple hostnames to different containers
- Serve a simple Node.js app, an Nginx static site, and a whoami test service
- View everything in your browser with zero port chaos!

---

## 🚀 Project Structure

- **Traefik** – Manages routing based on Docker labels
- **Whoami** – Test container that shows your request headers
- **App** – A Node.js container serving a basic HTML page
- **Blog** – An Nginx server serving a static HTML page

---

## 📦 Requirements

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/)
- Optional: [Colima](https://github.com/abiosoft/colima) if you're on macOS and not using Docker Desktop

---

## Add hostnames to /etc/hosts

- Traefik uses custom hostnames for routing. You must add these entries to your /etc/

hosts file:

```
127.0.0.1 whoami.localhost
127.0.0.1 app.localhost
127.0.0.1 blog.localhost
💡 On Windows, it's located at: C:\Windows\System32\drivers\etc\hosts
```

## Start the services
```
docker-compose up -d
```

## Visit your services:

- 🧭 Traefik Dashboard: http://localhost:8080

- 🧪 Whoami: http://whoami.localhost

- 🚀 Node App: http://app.localhost

- 📝 Blog (Nginx): http://blog.localhost