Title: Stage SIO2 

> **<u>FICHE DESCRIPTIVE :</u>**

> <u>**Dates du stage :**</u>
>
> - **Date début :** Janv 01/012026
> - **Date fin :** 13/02/2026
>
> **Entreprise :** CEREEP-Ecotron IleDeFrance (CNRS)

## Présentation de l’entreprise / société

**CEREEP – Ecotron Île-de-France** (Centre de Recherche en Écologie Expérimentale et Prédictive, UMS 3194) est une unité mixte de service portée par le CNRS, l’ENS-PSL et l’Université PSL, localisée à Saint-Pierre-lès-Nemours (Seine-et-Marne). Implantée sur un domaine de 78 ha, elle combine un bâtiment de recherche moderne, des espaces naturels, des capacités d'hébergement et plusieurs plateformes techniques au service de l’écologie expérimentale.

## 📑 Restitution de stage – Évolution et optimisation des outils

## 🔬 Contexte du stage

Pour ce second stage, l'objectif était de faire évoluer les outils développés l'an dernier. Alors que le premier stage portait sur l'acquisition de données historiques via NASA POWER, ce nouveau projet visait à :

- Intégrer une nouvelle source de données plus précise et locale via Open-Meteo.
- Préparer le terrain pour la comparaison entre les prévisions météo et les capteurs réels des chambres climatiques (Ecorium).
- Optimiser l'architecture logicielle (API et Base de données) pour supporter ces nouvelles fonctionnalités.

---

## 🛰️ Programme 1 : Script Python – Migration vers l’API Open-Meteo

Le premier programme est une évolution majeure du script d'acquisition :

- Transition d'API : Passage de NASA POWER à Open-Meteo pour obtenir des données en temps réel et des prévisions plus précises.
- Mapping des variables : Identification et correspondance des paramètres météo standards (température, humidité, vent) avec les besoins spécifiques des scientifiques.
- Standardisation : Conservation du format CSV normalisé et du système d'UID unique (hash MD5) pour assurer la compatibilité avec l'API existante.

👉 Difficulté : La compréhension des différents modèles de données météo et la sélection des paramètres pertinents parmi la vaste liste proposée par Open-Meteo.

---

## 🌐 Programme 2 : API Flask – Optimisation et nouvelles routes

Le deuxième programme a consisté à mettre à jour l'API REST pour gérer ces nouvelles données :

- Adaptation de la base de données : Modification des schémas SQLAlchemy pour inclure de nouveaux champs de métadonnées spécifiques à Open-Meteo.
- Amélioration des performances : Optimisation des requêtes pour filtrer les données plus rapidement, notamment lors de l'affichage de longues périodes.
- Étude de l'Ecorium : Analyse de la structure des logs de l'automate (SCADA) pour anticiper l'intégration future des mesures internes.

👉 Note technique : Bien que l'intégration complète des données de l'Ecorium n'ait pas été finalisée en raison de la complexité des protocoles de l'automate, une étude structurelle a été réalisée pour permettre un futur couplage.

---

## 💻 Programme 3 : Interface Web – Comparaison et Visualisation

L'interface a été enrichie pour offrir plus de flexibilité aux utilisateurs :

- Dashboard amélioré : Ajout de fonctionnalités de filtrage avancées.
- Visualisation dynamique : Mise à jour des graphiques Chart.js pour permettre la superposition de données provenant de sources différentes.
- Interface d'upload : Simplification du processus d'importation des fichiers de métadonnées.

---

## ⚙️ Apprentissage et outils utilisés

- API Open-Meteo : Apprentissage des requêtes sur une API de prévisions en temps réel.
- Python / Flask / SQLAlchemy : Approfondissement des compétences en maintenance évolutive de code existant.
- Analyse de données industrielles : Découverte des variables de supervision (tags) d'une chambre météorologique (Ecorium).
- Docker : Utilisation continue pour le déploiement et la gestion des environnements.

---

## ✅ Bilan personnel

Ce stage de deuxième année m'a permis de travailler sur la maintenance et l'évolution d'un projet réel, une situation très courante en entreprise.

### Compétences acquises

- Adaptabilité : Savoir modifier et améliorer un code que j'avais moi-même écrit un an plus tôt.
- Analyse technique : Savoir identifier les limites d'un système (comme la complexité de l'Ecorium) et se concentrer sur les priorités fonctionnelles.
- Expertise API : Maîtriser la transition entre deux fournisseurs de données différents tout en gardant une interface cohérente.

👉 Ce stage confirme mon intérêt pour le développement "Full-Stack" et la gestion de données scientifiques, tout en m'ayant confronté aux réalités techniques des systèmes industriels complexes.