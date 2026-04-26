# production-ready-kubernetes-platform

This is a hands-on project where I built a production-like Kubernetes platform from scratch using AWS, Terraform, GitHub Actions, Helm and Docker.

The goal here was simple: simulate what I actually do in real environments — build, automate and run reliable systems.

---

## what’s inside

* Node.js API with `/health` endpoint
* Dockerized application
* CI pipeline building images automatically (GitHub Actions)
* Image versioning using GHCR
* Helm chart for deployment
* Kubernetes-ready setup (with probes, resources and HPA)

---

## architecture (simplified)

GitHub → GitHub Actions → Docker image → GHCR
↓
Kubernetes (Helm)

---

## why I built this

I wanted a project that actually proves:

* I can build and automate infrastructure
* I understand CI/CD in practice (not just theory)
* I know how to run applications on Kubernetes properly
* I apply SRE basics like health checks, scaling and resource control

---

## running locally

```bash
cd app
npm install
npm start
```

```bash
curl http://localhost:3000/health
```

---

## docker

```bash
docker build -t sre-demo-api:local ./app
docker run -p 3000:3000 sre-demo-api:local
```

---

## kubernetes (helm)

```bash
helm upgrade --install sre-demo-api ./helm/app
kubectl get pods
```

---

## what I focused on

* keeping it simple but realistic
* using tools that are actually used in production
* making everything reproducible via code
* showing end-to-end flow (build → package → deploy)

---

## next steps

* add ingress + domain
* add TLS
* plug in real observability (Prometheus/Grafana or Datadog)
* possibly integrate ArgoCD for GitOps

---

## author

Marcus Jianni
DevOps / Cloud Engineer
