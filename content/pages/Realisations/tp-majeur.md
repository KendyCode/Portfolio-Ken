Title: TP majeur

[![GitHub](https://img.shields.io/badge/Code_Source-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/KendyCode/tp_api_serie_github)

## Première année de BTS SIO :

## TP Majeur – Recherche Films & Acteurs avec API TMDb

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

![Texte alternatif de l'image]({static}/images/batman.jpg){: .img-tp-majeur }

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
