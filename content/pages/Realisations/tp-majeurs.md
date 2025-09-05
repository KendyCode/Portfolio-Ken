Title: TP majeurs

# Présentation des travaux pratiques ou mini-projets :


## Première année de BTS SIO :
Title: TP Majeurs SIO

> **<u>FICHE DESCRIPTIVE :</u>**

> <u>**Thème du TP :**</u>  
>
> - **Sujet :** Gestion d’une base de données de pays  
> - **Langage :** PHP (PDO)  
> - **Base de données :** MySQL (tables `Country`, `City`)  
>
> **Objectif :** Manipuler et afficher des données issues d’une base relationnelle via des pages PHP dynamiques.  

---

## Présentation du projet

Ce TP consiste à créer une application web en PHP permettant de :  
- Récupérer et afficher la liste des **continents**,  
- Lister les **pays d’un continent** sélectionné,  
- Afficher leurs informations principales (nom, population, superficie, drapeau, capitale),  
- Consulter les détails d’un pays en particulier,  
- Mettre à jour certaines informations via un formulaire (ex. population, espérance de vie).  

---

## Organisation du code

### 📌 1. Fichier `db.php`
- Fonction `getContinent()` → récupère la liste des continents distincts.  
- Fonction `getCapitale($id)` → retourne le nom de la capitale d’un pays.  
- Fonction `getPaysByName($name)` → retourne toutes les informations d’un pays donné.  

---

### 📌 2. Fichier `index2.php`
- Vérifie la présence d’un paramètre `name` dans l’URL (`?name=Europe`).  
- Si présent → affiche les pays du continent correspondant.  
- Sinon → affiche tous les pays du monde.  
- Pour chaque pays affiché :  
  - Drapeau (image construite à partir du code ISO à 2 lettres),  
  - Nom, population, superficie,  
  - Capitale (via la fonction `getCapitale`).  

---

### 📌 3. Fichier `DetailsPays.php`
- Récupère le nom du pays passé en paramètre dans l’URL.  
- Affiche toutes ses informations.  
- Propose un **formulaire de mise à jour** (population, espérance de vie).  
- Si le formulaire est soumis :  
  - Vérifie les champs remplis,  
  - Construit une requête SQL `UPDATE`,  
  - Met à jour les données dans la base,  
  - Affiche un message de succès ou d’erreur.  

---

Title: TP Majeurs – Recherche Films & Acteurs avec API TMDb

> **<u>FICHE DESCRIPTIVE :</u>**
>
> <u>**Thème du TP :**</u>  
>
> - **Sujet :** Formulaires HTML et utilisation d’une API externe (TMDb)  
> - **Langages :** PHP, HTML/CSS  
> - **Outil externe :** The Movie Database (TMDb) API  
>
> **Objectif :** Créer une application permettant de rechercher des films et des acteurs à partir d’un formulaire HTML et d’afficher les résultats grâce à l’API TMDb.  

---

## Présentation du projet

Ce TP combine **formulaires HTML** et **appel à une API externe** afin de réaliser une recherche interactive :  
- Un formulaire recherche des **films** (`movie.php`).  
- Un autre formulaire recherche des **acteurs** (`name.php`).  
- Les données sont récupérées en **GET** (paramètre `query` dans l’URL).  
- Les résultats sont affichés (affiches de films, images de profils des acteurs).  

---

## Concepts HTML utilisés

### 1️⃣ Attributs d’un formulaire
- **`action`** → définit le fichier où sont envoyées les données (`movie.php` ou `name.php`).  
- **`method`** → mode d’envoi des données (`GET` ou `POST`).  
- **`name`** → identifiant du champ, utilisé pour récupérer sa valeur en PHP via `$_GET` ou `$_POST`.  

### 2️⃣ Différence entre `GET` et `POST`
- **GET** : envoie les informations directement dans l’URL (visible).  
- **POST** : envoie les informations en arrière-plan (non visibles, plus sécurisé).  

---

## Exemple de formulaires

```html
<!-- Formulaire de recherche de films -->
<form action="movie.php" id="search-movies" method="get">
  <input type="text" class="form-control ps-5 rounded-pill"
         placeholder="Search Films" name="query">
</form>

<!-- Formulaire de recherche d’acteurs -->
<form action="name.php" id="search-acteurs" method="get">
  <input type="text" class="form-control ps-5 rounded-pill"
         placeholder="Search Acteurs" name="query">
</form>


L’attribut action est différent selon la recherche :

movie.php → films

name.php → acteurs

L’utilisateur saisit une recherche, ex. "SONICLEGOAT", qui sera transmise à la page cible via $_GET["query"].


## Seconde année de BTS SIO :