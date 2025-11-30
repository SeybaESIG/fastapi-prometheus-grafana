# API FastAPI + Prometheus + Grafana (Monitoring conteneurisé)  

## Description  

Projet mettant en place une API Python (FastAPI) instrumentée avec Prometheus, accompagnée d’une stack de monitoring basée sur Prometheus et Grafana.  
L’objectif est de superviser des métriques essentielles d’une application conteneurisée, telles que le nombre total de requêtes HTTP ou la latence de traitement.  

## Fonctionnalités  

* API FastAPI avec endpoint de santé (/health)  
* Exposition de métriques Prometheus via /metrics  
* Stack de monitoring:  
  * Prometheus pour le scraping des métriques  
  * Grafana pour la visualisation  
* Orchestration complète via Docker Compose  
* Exemple de métriques disponibles:  
  * http_requests_total  
  * http_request_duration_seconds_bucket  

## Structure du projet  

```
fastapi-prometheus-grafana/
├── api/
│   ├── main.py
│   ├── requirements.txt
│   └── Dockerfile
├── monitoring/
│   └── prometheus.yml
├── docker-compose.yml
├── .gitignore
└── README.md
```

## Prérequis  

* Docker  
* Docker Compose  

## Installation et exécution  

1. Cloner le projet  

git clone [https://github.com/USERNAME/fastapi-prometheus-grafana.git](https://github.com/USERNAME/fastapi-prometheus-grafana.git)  
cd fastapi-prometheus-grafana  

2. Lancer les services  

docker compose up --build  

## Services disponibles  

API: [http://localhost:8000/health](http://localhost:8000/health)  
Metrics: [http://localhost:8000/metrics](http://localhost:8000/metrics)  
Prometheus: [http://localhost:9090](http://localhost:9090)  
Grafana: [http://localhost:3000](http://localhost:3000)  

## Configuration Grafana  

1. Se connecter à Grafana (admin / admin lors du premier accès).  
2. Aller dans Connections → Data sources → Add data source.  
3. Choisir Prometheus.  
4. Renseigner l’URL suivante: [http://prometheus:9090](http://prometheus:9090)  
5. Enregistrer avec Save & Test.  

6. Créer un dashboard:  
   Dashboards → New → New dashboard → Add a new panel.  

   Métries recommandées:
   * http_requests_total
   * http_request_duration_seconds_bucket  

## Licence  

Libre d’utilisation pour toute expérimentation ou amélioration personnelle.  


