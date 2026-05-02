# AsciiArtify – Kubernetes Local Development Concept

## 📌 Вступ

У цьому документі розглянуто три інструменти для локального розгортання Kubernetes кластерів:

- Minikube
- kind (Kubernetes IN Docker)
- k3d

Мета — обрати оптимальний інструмент для PoC стартапу AsciiArtify.

---

## ⚙️ Характеристики

| Характеристика | Minikube | kind | k3d |
|----------------|----------|------|-----|
| Тип | VM / Container | Docker-based | Docker-based (k3s) |
| Швидкість запуску | Середня | Висока | Дуже висока |
| Підтримка ОС | Linux, macOS, Windows | Linux, macOS, Windows | Linux, macOS, Windows |
| Kubernetes | Повний | Повний | Lightweight (k3s) |
| Автоматизація | Так | Так (CI-friendly) | Так |
| Вбудовані аддони | Так | Ні | Частково |
| Ресурси | Високі | Середні | Низькі |

---

## ✅ Переваги та недоліки

### 🔹 Minikube

**Переваги:**
- Повноцінний Kubernetes
- Багато аддонів (dashboard, ingress)
- Добра документація

**Недоліки:**
- Повільний запуск
- Високе споживання ресурсів
- Не ідеальний для CI

---

### 🔹 kind

**Переваги:**
- Дуже швидкий старт
- Ідеально для CI/CD
- Простий у використанні

**Недоліки:**
- Менше функцій
- Немає вбудованих аддонів
- Обмежений networking

---

### 🔹 k3d

**Переваги:**
- Найшвидший
- Легковаговий (k3s)
- Добре підходить для PoC

**Недоліки:**
- Менш "production-like"
- Менше документації ніж Minikube

---

## ⚠️ Docker ліцензія та Podman

Docker Desktop має обмеження ліцензії для комерційного використання.

Альтернатива:
- Podman (open-source, daemonless)

⚠️ Проблеми:
- не всі інструменти (kind, k3d) стабільно працюють з Podman
- можливі проблеми з socket API

Рекомендація:
- Для PoC використовувати Docker
- Для production розглянути Podman

---

## 🚀 Демонстрація (k3d)

## 🎥 Demo

<p align="center">
  <img src="./demo.gif" width="800"/>
</p>

### 1. Створення кластеру

```bash
k3d cluster create mycluster

