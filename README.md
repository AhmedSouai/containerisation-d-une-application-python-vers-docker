# Mini-projet : Student API + Website

## 🚀 Description du projet

Ce mini-projet illustre la **containerisation d’une application simple** composée de :  

- **Une API Python** servant des informations sur des étudiants (ex: âge, notes).  
- **Un site web PHP** consommant cette API pour afficher les données.  
- Communication entre les conteneurs via un **réseau Docker dédié**.  

L’objectif est de montrer **la mise en place d’une architecture multi-conteneurs**, la gestion des volumes et des variables d’environnement, ainsi que l’ordre de démarrage des services.

---

## 🧩 Architecture

- `api` (Python)  
  - Fournit une API REST simple
  - Conteneur : `student_api`
  - Port : `5000`  
  - Volume : JSON des données (`student_age.json`)  
  - Healthcheck possible pour garantir que l’API est opérationnelle avant le site

- `website` (PHP/Apache)  
  - Consomme l’API pour afficher les informations sur les étudiants
  - Conteneur : `student_web`
  - Port : `8080`
  - Dépend de l’API (`depends_on: api`)

- Réseau Docker : `student_network` pour la communication interne entre conteneurs

---

## 🎯 Objectifs pédagogiques

Ce projet permet de comprendre et pratiquer :  

1. **Containerisation** : isoler des applications dans des conteneurs Docker.  
2. **Orchestration simple** : gérer plusieurs conteneurs via `docker-compose`.  
3. **Volumes et persistance** : partager des fichiers entre l’hôte et le conteneur.  
4. **Variables d’environnement** : injecter des informations de configuration dans les conteneurs.  
5. **Ordre de démarrage (`depends_on`)** : contrôler la séquence de lancement des services.  

<img width="1083" height="332" alt="Capture d’écran 2026-02-10 005540" src="https://github.com/user-attachments/assets/88948636-26f1-4346-94ad-e0c244169157" />
