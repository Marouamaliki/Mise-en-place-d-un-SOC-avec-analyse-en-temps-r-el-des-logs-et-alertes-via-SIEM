# Mise-en-place-d'un-SOC-avec-analyse-en-temps-réel-des-logs-et-alertes-via-SIEM
# 🛡️ Mise en place d’un SOC avec la Stack ELK sur CentOS 9

## 📌 Contexte

Dans le cadre de notre formation en cybersécurité, ce projet vise à mettre en place un **Security Operations Center (SOC)** utilisant la **stack ELK (Elasticsearch, Logstash, Kibana)** sur un système CentOS 9. L’objectif est de centraliser, analyser et visualiser en temps réel les logs système, dans une démarche de détection proactive des incidents de sécurité.

---

## 🎯 Objectifs

- Installer et configurer la stack ELK sur CentOS 9.
- Centraliser les logs systèmes via Logstash.
- Visualiser et analyser les logs en temps réel avec Kibana.
- Assurer la sécurisation des échanges et l’accès à la plateforme.
- Réaliser une démonstration de détection d’événements suspects.

---

## 🧰 Environnement & Technologies

| Composant       | Version / Détail                 |
|-----------------|----------------------------------|
| OS              | CentOS Stream 9                  |
| Java            | OpenJDK 11                       |
| Elasticsearch   | 8.x                              |
| Logstash        | 8.x                              |
| Kibana          | 8.x                              |
| Outils réseau   | Firewalld, Netstat, Curl         |
| Protocoles      | Syslog, HTTP(S)                  |

---

## 🧱 Architecture du SOC

[ Hôtes / Machines clientes ]
|
(Syslog)
↓
[ Logstash ]
↓
[ Elasticsearch ]
↓
[ Kibana ]


## ⚙️ Étapes de mise en œuvre

### 1. Préparation du système
- Mise à jour du système
- Installation de Java OpenJDK 11

### 2. Installation d’Elasticsearch
- Ajout du dépôt officiel Elastic
- Configuration de `elasticsearch.yml`
- Ouverture des ports nécessaires (9200)

### 3. Installation de Logstash
- Configuration d’un pipeline d’ingestion de logs syslog
- Test d’envoi de logs avec `logger`

### 4. Installation de Kibana
- Lien avec Elasticsearch
- Accès via navigateur (port 5601)

### 5. Sécurisation de la plateforme
- Authentification dans Kibana
- Communication chiffrée SSL/TLS
- Définition des rôles utilisateurs

---

## 📊 Résultats obtenus

- Centralisation des logs des hôtes cibles
- Tableaux de bord dynamiques sur Kibana
- Alertes personnalisées sur événements suspects (ex. connexions SSH multiples)

---

## 🧠 Difficultés rencontrées

| Problème                                | Solution apportée                           |
|-----------------------------------------|----------------------------------------------|
| Logstash ne reçoit pas les logs         | Vérification des ports et format Syslog      |
| Incompatibilité Java                    | Installation de Java 11 (OpenJDK recommandé) |
| Problèmes de certificats SSL            | Création de certificats auto-signés          |

---
