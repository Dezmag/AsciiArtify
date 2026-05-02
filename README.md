# AsciiArtify

> Kubernetes PoC for AI-based Image → ASCII conversion system

<p align="center">
  <img src="AsciiArtify/demo.gif" width="800"/>
</p>

---

## 📌 Overview

AsciiArtify is a Proof of Concept project exploring local Kubernetes environments for deploying and testing a future ML-based ASCII-art generator.

The goal is to evaluate lightweight Kubernetes solutions for development and CI/CD workflows.

---

## ⚙️ Kubernetes Local Tools Comparison

| Tool     | Architecture      | Startup Speed | Resource Usage | Best Use Case |
|----------|------------------|---------------|----------------|--------------|
| Minikube | VM-based         | Medium        | High           | Learning     |
| kind     | Docker-based     | Fast          | Medium         | CI/CD        |
| k3d      | k3s + Docker     | Very Fast     | Low            | PoC / Dev    |

---

## 🏆 Recommendation

For this PoC, **k3d** is recommended because:

- ⚡ Fast cluster creation
- 🪶 Lightweight (k3s)
- 🐳 Docker-native workflow
- 🔁 Perfect for rapid testing

---

## 🚀 Quick Start

```bash
k3d cluster create mycluster

kubectl apply -f demo/deployment.yaml
kubectl apply -f demo/service.yaml

kubectl get pods
kubectl get svc
