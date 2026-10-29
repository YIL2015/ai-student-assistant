# 🤖 AI Student Assistant

Compagnon d'étude IA pour les étudiants de l'EPHEC. Il **explique sans donner la réponse**, **organise les études** (rappels, deadlines Moodle, notifications) et dialogue via un **mini-robot Raspberry Pi**.

> Projet d'intégration 2026-2027 · Groupe G5 – Agent IA
> ⚠️ Dépôt de **proposition** : il présente une réorganisation du wiki et du backlog de [T3042-projet-integration](https://github.com/4B-cycle/T3042-projet-integration). Le groupe doit la valider avant de la reprendre.

## 📚 Documentation

| | |
|---|---|
| 🏠 Wiki | [Accueil](../../wiki) |
| 📋 Backlog vivant | [GitHub Project](https://github.com/users/4B-cycle/projects/1) · [vue d'ensemble](../../wiki/Backlog) |
| 🏗️ Architecture | [Architecture](../../wiki/Architecture) · [Choix techniques](../../wiki/Choix-techniques) |
| 🛠️ Installer | [Installation et utilisation](../../wiki/Installation-et-utilisation) |
| 🔧 Améliorations proposées | [Liste](../../wiki/Améliorations-proposées) |

## Architecture en bref

```text
Étudiant ─▶ Open WebUI (orchestrateur + RAG) ─▶ LLM Mistral Small (Azure)
                    │ MCP
                    ▼
            Serveur MCP Python ─▶ Backend API + PostgreSQL
                    ├─▶ Moodle (calendrier iCal)
                    └─▶ ntfy ─▶ 📱 notifications
Robot Raspberry Pi ─(Wi-Fi)─▶ serveur
```

## Structure proposée du dépôt

```text
mcp-server/   outils MCP (rappels, Moodle, exercices…)
backend/      API FastAPI + PostgreSQL
robot/        scripts du Raspberry Pi
docs/         schémas, maquettes
```
