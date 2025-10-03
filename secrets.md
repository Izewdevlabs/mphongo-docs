# 🔐 GitHub Secrets Reference
# 🔐 Secrets Reference for Mphongo Network AI

This document explains the purpose and usage of all environment secrets across the Mphongo ecosystem.

---

## 📦 Common Across All Repos

| Variable             | Used In                    | Description                                  | Where to Get It                    |
|----------------------|----------------------------|----------------------------------------------|------------------------------------|
| `NODE_ENV`           | All                        | Node.js environment (development/production) | Manual                             |
| `PORT`               | All backend services       | Port for the server to listen on             | Default to 3000 or 8000           |

---

## ☁️ AWS Credentials

| Variable             | Used In                    | Description                                  | Where to Get It                    |
|----------------------|----------------------------|----------------------------------------------|------------------------------------|
| `AWS_ACCESS_KEY_ID`     | `mphongo-ci-cd`, `core-api`, others | Access key for AWS services      | IAM Console                        |
| `AWS_SECRET_ACCESS_KEY` | `mphongo-ci-cd`, `core-api`, others | Secret for AWS services          | IAM Console                        |
| `AWS_REGION`             | Deployment targets      | AWS region e.g. `us-east-1`                 | AWS Console                        |

---

## 🧠 OpenAI / AI Services

| Variable               | Used In                  | Description                          | Source                    |
|------------------------|--------------------------|--------------------------------------|---------------------------|
| `OPENAI_API_KEY`       | music-generator, vocal-engine, mastering-engine | API key for generative AI models | https://platform.openai.com/account/api-keys |
| `HUGGINGFACE_TOKEN`    | mastering-engine         | Token for downloading models         | https://huggingface.co/settings/tokens |

---

## 🔐 GitHub Actions Secrets to Set

Each repo must go to **Settings → Secrets and Variables → Actions** and set the required secrets:

- `AWS_ACCESS_KEY_ID`
- `AWS_SECRET_ACCESS_KEY`
- `OPENAI_API_KEY`
- `HUGGINGFACE_TOKEN`

Each repo will also have its own `.env.example` listing only the secrets relevant to that project.

---

## 🌐 Shared Across All Repos
- `NODE_ENV`: Usually `production` or `development`
- `JWT_SECRET`: Used for token signing
- `DATABASE_URL`: Full DB URI (optional if using individual variables)

## 🧠 AI Engine Specific
- `HF_API_KEY`: HuggingFace key (Music Generator, Vocal, Mastering)
- `OPENAI_API_KEY`: For TTS/transcription (if used)

## ☁️ AWS
- `AWS_ACCESS_KEY_ID`: S3 or Polly/Transcribe
- `AWS_SECRET_ACCESS_KEY`

## 🐳 CI/CD & Docker
- `DOCKER_USERNAME`
- `DOCKER_PASSWORD`

## 🔑 Optional
- `DEPLOY_TOKEN`: For triggering remote auto deploys (e.g., Railway, Render)
