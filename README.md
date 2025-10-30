# Dashboard de suivi & gestion de parc machine – ETI françaises

**Projet :** Plateforme « ParcMachine »
**Auteur :** Côme
**Version :** 0.1
**Date :** YYYY-MM-DD

---

## 1. Contexte & problématique

De nombreuses entreprises de taille intermédiaire (ETI) françaises s’appuient sur un parc machine (machines de production, équipements de maintenance, outillages, etc.). Le suivi de ce parc, la gestion des états, la planification de la maintenance, le monitoring des indicateurs clés et la visibilité globale sont souvent dispersés (tableurs, papier, outils hétérogènes). Cela génère :

* un manque de visibilité consolidée sur l’état global du parc machine,
* des actions de maintenance réactives plutôt que proactives,
* des difficultés à piloter les coûts d’exploitation, les temps d’immobilisation, les indicateurs de performance machine (OEE, MTBF, MTTR…),
* des échanges peu fluides entre les équipes techniques, de maintenance et la direction.

**Objectif principal** : proposer une plateforme simple, ergonomique, intuitive, dédiée aux ETI, pour centraliser la gestion du parc machine, visualiser les indicateurs clés, planifier et suivre la maintenance, et faciliter la prise de décision.

---

## 2. Vision produit

« ParcMachine » permet aux responsables maintenance, chefs d’atelier, directeurs techniques et équipes de superviser en temps quasi-réel leur parc machine. Grâce à un dashboard clair, ils visualisent l’état des équipements, les indicateurs de performance, les alertes et peuvent déclencher des actions. L’outil est pensé pour être déployé rapidement dans une ETI, avec peu de friction, tout en étant extensible.

**Valeur ajoutée** :

* Visibilité immédiate et centralisée du parc machine.
* Réduction des temps d’immobilisation et des coûts liés à la maintenance non planifiée.
* Meilleur pilotage des performances machine et comparaison entre équipements.
* Renforcement de la collaboration entre maintenance et direction.

---

## 3. Utilisateurs cibles & personas

### Persona 1 : Responsable maintenance « Pierre »

* Environnement : ETI de 300 salariés, parc de 50 machines.
* Objectifs : réduire les arrêts non planifiés, optimiser les coûts de maintenance, démontrer les gains à la direction.
* Besoins : état global des machines, alertes sur dérives, historique maintenance, indicateurs simples.

### Persona 2 : Chef d’atelier « Sophie »

* Environnement : supervise directement les opérateurs, doit réagir vite.
* Objectifs : avoir une vue claire des machines actuellement indisponibles, planifier les interventions et communiquer rapidement.
* Besoins : dashboard facile, liste des machines critiques, actions à venir, notifications.

### Persona 3 : Directeur technique « Marc »

* Environnement : membre de la direction, souhaite piloter la performance globale.
* Objectifs : suivre les KPI (OEE, MTBF, MTTR…), comparer machines/sites, prendre des décisions d’investissement.
* Besoins : vue agrégée, export de données, rapports visuels, benchmarking.

---

## 4. Principes du produit

* Simplicité et ergonomie avant tout : interface claire, peu d’effort à former.
* Modularité et extensibilité : possibilité d’ajouter de nouveaux modules (capteurs IoT, maintenance prédictive…) sans remise à zéro.
* Fiabilité et temps réel : les données doivent être à jour, les alertes déclenchées rapidement.
* Sécurité et respect des données : authentification, profils d’utilisateur, droits d’accès.
* Compatibilité : usage web (desktop + tablette), API ouverte pour intégration.

---

## 5. Fonctionnalités clés

### 5.1. Dashboard principal

* Vue synthétique du parc machine : nombre total de machines, nombre de machines en panne, machines en maintenance, taux de disponibilité global.
* Graphiques d’évolution : disponibilité, MTBF, MTTR sur les 30 jours, 90 jours.
* Carte ou tableau par site (si multi-site).
* Liste des alertes actuelles (pannes, dépassements seuils, maintenance à venir).

### 5.2. Module « Machines »

* Liste de toutes les machines (filtrable par site, type, statut).
* Fiche machine : identification (site, ligne, type, date d’installation), statut actuel, historique interventions, indicateurs propres machine (ex : disponibilité, taux d’utilisation).
* Possibilité d’ajouter/modifier une machine.

### 5.3. Module « Maintenance & Interventions »

* Planning des interventions prévues (maintenance préventive, calibrage, etc.).
* Création d’une intervention : machine concernée, type, priorité, date prévue, responsable.
* Historique des interventions passées avec résultat, durée, coût.
* Statistiques : nombre d’interventions par machine, temps moyen, coût moyen.

### 5.4. Module « Indicateurs & Rapports »

* KPI clés pré-définis : OEE (Overall Equipment Effectiveness), MTBF (Mean Time Between Failures), MTTR (Mean Time To Repair), taux de disponibilité, taux d’utilisation.
* Rapports exportables (PDF, CSV) pour la direction.
* Comparaison inter-machines ou inter-sites.

### 5.5. Module « Alertes & Notifications »

* Définition de seuils (ex : disponibilité < 90 %, temps arrêt > xx h).
* Notifications par email / in-app pour les utilisateurs concernés.
* Tableau de bord des alertes actives.

### 5.6. Sécurité & Administration

* Authentification (LDAP/SSO ou simple compte).
* Gestion des rôles (maintenance, chef d’atelier, direction) et droits d’accès.
* Journalisation des actions (audit).
* Paramétrage des sites, machines, utilisateurs.

---

## 6. Exigences non fonctionnelles

* Performance : l’affichage du dashboard principal doit se charger en moins de 2 s pour un parc de 500 machines.
* Disponibilité : l’application doit vis-à-vis être disponible 99,5 % du temps (hors maintenance).
* Sécurité : conformité GDPR pour les données utilisateurs, chiffrement des données sensibles.
* Compatibilité : navigateur modernes (Chrome, Edge, Firefox) + usage tablette.
* Scalabilité : capable de monter jusqu’à 1000 machines / multi-sites.
* Intégration : API REST pour échange de données avec ERP/maintenance externe.

---

## 7. Scope & ce qui n’est pas inclus

**Inclus dans cette version 1.0**

* Dashboard principal + modules Machines, Maintenance, Rapports, Alertes.
* Authentification, rôles utilisateurs, export de base.
* Données manuelles (pas encore capteurs IoT en temps réel).
* Déploiement sur un unique site pilote.

**Exclu (version ultérieure)**

* Intégration IoT en temps réel (capteurs, prédiction automatique).
* Module mobile natif (iOS / Android).
* Intelligence artificielle pour maintenance prédictive.
* Multi-tenant hébergé SaaS avec gestion clients multiples.

---

## 8. Critères de succès & KPIs

* Délai d’implémentation dans l’ETI pilote : < 3 mois.
* Adoption : ≥ 80 % des machines référencées dans le système.
* Réduction des arrêts non planifiés de : > 10 % après 6 mois.
* Satisfaction utilisateur (maintenance + direction) : score ≥ 4/5.
* Temps moyen d’une requête sur dashboard principal : < 2 s.

---

## 9. Roadmap & jalons

| Phase                                | Date estimée  | Livrables principaux                       |
| ------------------------------------ | ------------- | ------------------------------------------ |
| Phase 0 : cadrage & architecture     | Semaine 1-2   | Spécifications techniques, choix stack     |
| Phase 1 : MVP                        | Semaine 3-10  | Modules Dashboard, Machines, Maintenance   |
| Phase 2 : Rapports & Alertes         | Semaine 11-14 | Module Rapports, Alertes, notifications    |
| Phase 3 : Tests & déploiement pilote | Semaine 15-18 | Tests utilisateurs, corrections, MVP livré |
| Phase 4 : Retours & améliorations    | Semaine 19-22 | Ajustements, préparation version 1.1       |

---

## 10. Stack technologique (suggestion)

* Front-end : React.js ou Vue.js.
* Back-end : Node.js (Express) ou Python (Django/Flask).
* Base de données : PostgreSQL (relationnelle) ou MariaDB.
* API REST pour échanges.
* Authentification : JWT/OAuth 2.0.
* Déploiement : conteneurs Docker, Kubernetes ou service cloud (Azure, AWS, GCP).
* Visualisation : charting (ex : Chart.js, D3.js).
* Hébergement & CI/CD : GitHub Actions ou GitLab CI, pipeline automatisée.

---

## 11. Prompt pour Codex

> « Tu es un ingénieur logiciel et tu vas générer l’architecture complète, le squelette de code, les fichiers principaux (front-end + back-end) pour la plateforme “ParcMachine” décrite ci-dessus. Suis les spécifications du README. Crée une arborescence de projet, initialise le repository Git, intègre une API REST basique, une page dashboard avec un exemple de graphique, un modèle de machine dans la base de données, une route pour lister les machines, une route pour créer une intervention, et une authentification simple. Le code doit être commenté et structuré. Enfin, génère un README minimal pour le développeur. »

---

## 12. Risques & Dépendances

* Risque : manque d’adoption/utilisation des utilisateurs clés (maintenance) → prévoir formation & accompagnement.
* Dépendance : données existantes de l’ETI (machines, historiques) doivent être accessibles pour charger le système.
* Risque technique : intégration future IoT/predictive est plus complexe que prévu → prévoir architecture extensible.
* Risque budget-temps : délais de déploiement trop longs → maintenir focus sur MVP simple.

---

## 13. Glossaire

* OEE : Overall Equipment Effectiveness.
* MTBF : Mean Time Between Failures.
* MTTR : Mean Time To Repair.
* ETI : Entreprise de Taille Intermédiaire.
* API : Application Programming Interface.
* MVP : Minimum Viable Product.

---


