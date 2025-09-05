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




## Bilan et compétences acquises

### 🌍 1. Script Python de récupération et de formatage des données depuis l’API de la NASA
J’ai développé un **script automatisé en Python** interagissant avec l’API POWER de la NASA pour télécharger et structurer des données météorologiques (température, précipitations, etc.) sur un point géographique donné.  

**Fonctionnalités principales :**
- Récupération des données via une requête HTTP,  
- Formatage des dates selon le type temporel (horaire, journalier, mensuel…),  
- Ajout de métadonnées (coordonnées, période d’étude, UID unique),  
- Enregistrement dans un **fichier CSV structuré**, prêt à l’importation dans une base de données (ex. phpMyAdmin),  
- Gestion des cas particuliers comme les moyennes climatologiques,  
- Mesure et affichage du **temps d’exécution complet**.  

---

### 🛠️ 2. API Flask pour la gestion des données climatiques
J’ai conçu une **API REST en Python avec Flask** afin de centraliser la gestion des données climatiques.  

**Fonctionnalités principales :**
- Upload de fichiers CSV avec extraction automatique des métadonnées,  
- Consultation des données (tous les jeux de données ou un seul via un UID),  
- Filtrage des données sur une période donnée,  
- Mise à jour des métadonnées via une requête JSON,  
- Suppression d’un ou plusieurs fichiers (avec leurs données associées).  

**Technologies utilisées :**
- **Flask** pour l’API,  
- **SQLAlchemy** pour la gestion de la base de données,  
- **Pandas** pour le traitement et la manipulation des fichiers CSV.  

---

### 🖥️ 3. Interface Web interactive de visualisation et de gestion
Enfin, j’ai développé une **interface web complète en HTML/JavaScript** permettant d’interagir de façon intuitive avec les données.  

**Fonctionnalités principales :**
- Affichage des fichiers disponibles sous forme de tableau,  
- Actions possibles : édition, suppression, téléchargement, visualisation graphique,  
- Génération de **graphiques interactifs** avec Chart.js (zoom, sélection de paramètres),  
- Téléversement de nouveaux fichiers CSV via un formulaire dédié,  
- Communication avec l’API Flask pour synchroniser toutes les actions côté serveur.  

---

### ✅ Compétences acquises
Au cours de ce stage, j’ai renforcé mes compétences dans plusieurs domaines :  
- **Programmation en Python** (automatisation, API REST, gestion des données),  
- **Manipulation et traitement de données** (Pandas, SQL, CSV),  
- **Développement web** (HTML, JavaScript, Chart.js),  
- **Architecture client-serveur** (API Flask + interface web),  
- **Gestion de projet informatique** (structuration, modularité, documentation),  
- **Compétences transversales** : autonomie, rigueur, travail en équipe, communication technique.  
 
