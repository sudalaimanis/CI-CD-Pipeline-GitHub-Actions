
# 🚀 Node.js CI/CD Pipeline with GitHub Actions and Docker

This project demonstrates how to automate the CI/CD process for a sample Node.js application using **GitHub Actions** and **DockerHub**.

## 📦 Tech Stack

- Node.js 18 (Alpine)
- Docker & DockerHub
- GitHub Actions
- npm

---

## 📁 Project Structure

```
.
├── Dockerfile
├── package.json
├── app.js (or server.js)
└── .github
    └── workflows
        └── main.yml
```

---

## ⚙️ CI/CD Pipeline Workflow

Defined in `.github/workflows/main.yml`

### 🔁 Trigger
- On `push` to the `main` branch

### 🛠️ Jobs
1. **Checkout Code**
2. **Set up Node.js**
3. **Install Dependencies**
4. **Run Tests**
5. **Log in to DockerHub**
6. **Build Docker Image**
7. **Push Docker Image to DockerHub**

---

## 🔐 GitHub Secrets Required

Go to your GitHub repo → **Settings → Secrets and Variables → Actions → New repository secret**

| Name                | Description                            |
|---------------------|----------------------------------------|
| `DOCKERHUB_USERNAME`| Your DockerHub username                |
| `DOCKERHUB_TOKEN`   | Your DockerHub access token (not password) |

> 📝 Generate your token at: https://hub.docker.com/settings/security

---

## 🐳 Docker Reference Commands

```bash
# Build Docker image
docker build -t your-username/sample-node-app .

# Log in to DockerHub
docker login -u your-username

# Push image to DockerHub
docker push your-username/sample-node-app
```

---

## ✅ How to Use

1. Clone or fork the repo
2. Add the required GitHub Secrets
3. Commit and push to the `main` branch
4. CI/CD will automatically build, test, and push your Docker image

---

## 🧪 Local Testing

To simulate GitHub Actions locally, use [`act`](https://github.com/nektos/act):

```bash
act push
```

---

## 📦 DockerHub Output

After successful deployment, the image will be available at:

```
https://hub.docker.com/repository/docker/sudalaimmanis/sample-node-app
```

---

## 🙌 Contributing

Feel free to contribute by improving the workflow, adding more environments, or improving test coverage!

---

## 📬 Contact

Need help? Open an issue or reach out via email.

Happy Deploying! 🚀
