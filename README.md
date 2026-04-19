# 🗳️ Distributed Voting App - Dockerization et Orchestration

![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Docker Swarm](https://img.shields.io/badge/docker_swarm-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![PostgreSQL](https://img.shields.io/badge/postgresql-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)

## 📋 Présentation du projet
Ce projet consiste en la **modernisation d'une architecture distribuée** de vote en temps réel. L'objectif était de transformer une application lancée par scripts manuels en une infrastructure conteneurisée robuste, scalable et hautement disponible.

## 🏗️ Architecture Technique
L'application repose sur cinq microservices interconnectés :
* **Vote** (Python 3.11) : Interface utilisateur pour l'émission des votes.
* **Redis** : File d'attente (message broker) pour la collecte des données.
* **Worker** (.NET 7) : Service de traitement des données vers la base persistante.
* **PostgreSQL** : Stockage final des votes avec **persistance des données**.
* **Result** (Node.js 18) : Dashboard de visualisation en temps réel.

## 🛠️ Réalisations et Points Clés
* **Optimisation Docker** : Écriture de `Dockerfile` respectant les **bonnes pratiques** (images légères, gestion des environnements).
* **Orchestration avec Docker Compose** : Centralisation des services, gestion des volumes pour la **persistance** et isolation via des réseaux virtuels dédiés.
* **Résilience** : Mise en œuvre de **sondes de santé (healthchecks)** et gestion fine des dépendances entre services.
* **Déploiement Cluster (Swarm)** : Configuration d'un cluster **Docker Swarm** (1 Manager et 2 Workers) pour assurer la haute disponibilité et la tolérance aux pannes.

## 🚀 Installation et Lancement
1. **Clonage du dépôt** :
   ```bash
   git clone https://github.com/Ahmadou-D/Projet-Dockerization-et-Orchestration.git
