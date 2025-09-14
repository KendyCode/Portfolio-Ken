Title: Stage SIO1

> **<u>FICHE DESCRIPTIVE :</u>**

> <u>**Dates du stage :**</u>
>
> - **Date début :** 19/05/2025
> - **Date fin :** 28/06/2025
>
> **Entreprise :** CEREEP-Ecotron IleDeFrance

## Présentation de l’entreprise / société

**CEREEP – Ecotron Île-de-France** (Centre de Recherche en Écologie Expérimentale et Prédictive, UMS 3194) est une unité mixte de service portée par le CNRS, l’ENS-PSL et l’Université PSL, localisée à Saint-Pierre-lès-Nemours (Seine-et-Marne). Implantée sur un domaine de 78 ha, elle combine un bâtiment de recherche moderne, des espaces naturels, des capacités d'hébergement et plusieurs plateformes techniques au service de l’écologie expérimentale.

### Missions et services

- Soutien à la **recherche**, à l’**enseignement** et à la **formation** en écologie, en proposant hébergement, logistique, personnel technique et accès aux infrastructures.
- Gestion de l’**Écotron Île-de-France**, une infrastructure de pointe composée d’Ecolabs modulaires (environ 13 m³ chacun) permettant de maîtriser les conditions environnementales (température, humidité, lumière, composition gazeuse…) pour étudier des écosystèmes confinés, terrestres ou aquatiques.
- Pilotage de la plateforme **PLANAQUA**, qui regroupe des microcosmes, mésocosmes et macrocosmes (jusqu'à 750 m³) pour l’étude durable des systèmes aquatiques à différentes échelles.

### Enjeux scientifiques et position stratégique

- Trois grands axes scientifiques : experimental setup de modèles écologiques, étude des systèmes complexes et interactions physiologiques, écologiques et évolutives.
- Contribution aux enjeux majeurs : changement climatique, perte de biodiversité, services écosystémiques durables.
- Ouverture à la communauté de recherche nationale et internationale, en collaboration avec les réseaux **AnaEE-France / Europe**, **ReNSEE**, et en lien avec l’Écotron de Montpellier. Soutien institutionnel multiple (CNRS, région, Europe).
- Infrastructure labellisée, avec un bâtiment HQE inauguré en 2016, alliant performance écologique et excellence scientifique.

## 📑 Restitution de stage – Présentation des programmes développés

## 🔬 Contexte du stage

Dans le cadre de mon stage au **CNRS**, j’ai travaillé avec des scientifiques qui réalisent des expériences dans une **chambre météorologique**.  
Ils m’ont demandé de développer un ensemble d’outils pour :

- Créer un **script Python** qui interagit avec l’API météo **NASA POWER** afin de récupérer des données climatiques et d’enregistrer les résultats dans des fichiers CSV.
- Développer une **API Flask** capable d’interagir avec ces fichiers CSV.
- Mettre en place une **base de données** pour stocker et gérer les fichiers CSV et leurs métadonnées.
- Concevoir un **site web** permettant de visualiser les données sous forme de graphiques interactifs.

---

## 🛰️ Programme 1 : Script Python – récupération et formatage des données NASA POWER

Le premier programme est un **script Python** qui :

- envoie des requêtes à l’API NASA POWER avec les bons paramètres (coordonnées, période, type temporel : horaire, journalier, mensuel, climatologie),
- récupère les résultats au format JSON,
- **formate les données** (dates particulières, moyennes, climatologie),
- ajoute des **métadonnées** (coordonnées, type de fichier, période couverte),
- calcule un **UID unique** basé sur un hash MD5 pour identifier chaque fichier,
- enregistre le tout dans un **fichier CSV normalisé**.

👉 Exemple de difficulté : pour le mode _climatology_, les dates étaient renvoyées sous forme de texte (ex. `JAN`).  
J’ai dû choisir un format de début et de fin arbitraire, après discussion avec mon tuteur.

---

## 🌐 Programme 2 : API Flask – gestion des données climatiques

Le deuxième programme est une **API REST** construite avec **Flask**.  
Elle permet d’interagir avec les fichiers CSV et la base de données.

### Fonctionnalités

- **Upload** : import d’un fichier CSV avec extraction et stockage automatique des métadonnées.
- **Lecture** : récupération de tous les fichiers ou d’un fichier spécifique via son UID.
- **Filtrage** : sélection des données selon une période donnée.
- **Mise à jour** : modification des métadonnées via une requête JSON.
- **Suppression** : suppression d’un ou plusieurs fichiers (CSV + métadonnées).

👉 J’ai utilisé **SQLAlchemy** comme ORM :

- plus simple et lisible que du SQL pur,
- assez puissant et flexible pour ce projet.

👉 L’API est conçue pour être **réutilisable** : n’importe qui peut développer sa propre interface pour l’exploiter.

---

## 💻 Programme 3 : Interface Web – visualisation et interaction

Enfin, j’ai développé une **interface web** pour interagir graphiquement avec l’API Flask.

### Fonctionnalités

- Affichage en **tableau** des fichiers disponibles avec leurs métadonnées.
- Actions disponibles : édition (popup JSON modifiable), suppression, téléchargement, ajout d’un CSV.
- **Graphiques interactifs** avec Chart.js (sélection de paramètres, zoom, exploration des données).
- Import et lecture directe de nouveaux CSV via formulaire.

---

## ⚙️ Apprentissage et outils utilisés

- **Flask** : création d’API REST et gestion des routes.
- **SQLAlchemy** : interactions avec la base relationnelle.
- **Postman** : test des routes et endpoints.
- **MySQL + phpMyAdmin** : gestion des données et des métadonnées.
- **Docker** : déploiement en conteneurs (API, base de données, interface web).  
  👉 Problème rencontré : conflit de port → solution en externalisant et configurant les ports.

- **Bonnes pratiques** : documentation en anglais, code clair et structuré.
- **Réunions hebdomadaires** avec mon tuteur pour valider mes choix techniques.

---

## ✅ Bilan personnel

Au début du stage, j’étais dans le flou et je craignais la complexité du projet.  
Avec de la persévérance, des ressources (YouTube, ChatGPT) et l’aide de mon tuteur, j’ai progressé étape par étape.

### Compétences acquises

- Structurer un projet complet (acquisition → stockage → visualisation).
- Faire interagir différents systèmes (**API ↔ base de données ↔ interface web**).
- Faire des **choix techniques pertinents** (ORM, formats de dates, UID).
- **Documenter** et rendre le code réutilisable.

👉 Ce stage m’a permis de développer de solides compétences en **développement logiciel**, en **manipulation de données** et en **déploiement**, tout en renforçant mon autonomie et ma capacité à résoudre des problèmes concrets.
