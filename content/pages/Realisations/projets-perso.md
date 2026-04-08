Title: Projets personnels

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>

# 🎧 Projet : Music Log – Plateforme Interactive de Critiques Musicales

## 1. 📖 Présentation Générale

Le projet **Music Log** est une application web interactive conçue comme un "SensCritique" ou "Letterboxd" de la musique. Elle permet aux passionnés de rechercher des morceaux et de partager leurs critiques (notes et commentaires).

L'originalité et la force majeure de ce projet résident dans son **interconnexion avec l'API publique de Deezer**. Au lieu de stocker et de gérer manuellement un catalogue statique exhaustif, l'application agit comme une surcouche sociale intelligente sur le catalogue mondial de Deezer, combinant ainsi l'infinité d'une API externe avec la précision d'une base de données relationnelle locale.

---

<div id="carouselExample" class="carousel slide" data-bs-ride="carousel" style="max-width: 800px; margin: auto;">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="{static}/images/galleries_projet_perso_1/simple_search_music.jpg" class="d-block w-100" alt="Description 1">
    </div>
    <div class="carousel-item">
      <img src="{static}/images/galleries_projet_perso_1/dashboard_music_log.jpg" class="d-block w-100" alt="Description 2">
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
  </button>
</div>

## 2. 🏗️ Architecture Fonctionnelle

Le système repose sur une logique hybride innovante, structurée autour de **trois piliers principaux** :

### A. 🔄 L'Interconnexion Deezer et la Logique de Surcouche

- **Priorité aux données locales (Override) :** Lors d'une recherche, le système interroge l'API Deezer. Cependant, avant l'affichage, il vérifie si le `deezer_id` existe dans la base locale (`Track.query.filter_by(deezer_id=...)`). Si oui, les informations stockées en local écrasent celles de l'API. Cela permet à la modération de corriger des métadonnées ou de personnaliser l'affichage.
- **Ajout Administrateur (Pré-remplissage) :** L'ajout manuel d'une piste par un admin nécessite un `deezer_id` existant. Cela sert à "pré-enregistrer" ou "modifier en avance" l'apparence d'un morceau de Deezer sur Music Log, garantissant le bon fonctionnement du système de notation basé sur les appels API de cet ID.

---

### B. 🗄️ Le Modèle de Données (Base de données locale)

Le projet s'articule autour de trois tables principales (`models.py`) :

- **User (Utilisateur) :** Sauvegarde le nom d'utilisateur, l'email, le mot de passe hashé, ainsi qu'un flag `is_admin` pour la gestion des droits.
- **Track (Morceau) :** Enregistre les informations essentielles (identifiant Deezer, titre, artiste, pochette). **Logique de cache intelligente :** un morceau n'est inséré en BDD que lorsqu'un utilisateur décide de laisser un avis dessus pour la première fois.
- **Review (Avis) :** Contient la note (sur 5), le texte du commentaire et la date. Relié par clés étrangères à l'utilisateur (`user_id`) et au morceau (`track_id`).

---

### C. 👥 Les Espaces et Fonctionnalités

- **Recherche et Consultation :** Accès public à la recherche (via API en direct) et aux pages détails des morceaux avec extrait audio et avis de la communauté.
- **Espace Utilisateur :** Inscription/Connexion pour rédiger, consulter, éditer ou supprimer ses propres critiques.
- **Dashboard Administrateur :** Espace restreint pour visualiser l'ensemble des données, ajouter/modifier/supprimer des musiques (avec suppression en cascade des avis) et modérer les commentaires des utilisateurs.

---

## 3. ⚙️ Réalisation Technique

Le développement a couvert l'ensemble des couches de l'application, du front-end à la consommation d'API.

### 🌐 Consommation d'API REST
Utilisation de la bibliothèque Python `requests` pour interroger dynamiquement l'API de Deezer (api.deezer.com) pour la recherche et la récupération des détails des morceaux.

### 💾 Back-end & Persistance
Création des contrôleurs avec **Flask** et modélisation via l'ORM **SQLAlchemy**. Optimisation de la base de données locale MySQL pour limiter le stockage aux seuls morceaux critiqués (mise en cache).

### 🔐 Sécurité et Contrôle d'Accès (RBAC)
- Implémentation de la gestion des droits via des décorateurs (`@login_required`, `@admin_required`) pour séparer les rôles (visiteurs, utilisateurs, admin).
- Chiffrement sécurisé des mots de passe via **Werkzeug**.
- Protections contre les failles CSRF assurées par **Flask-WTF**.

### 💻 Front-end et Interface
Conception d'interfaces web dynamiques en utilisant le moteur de templating **Jinja2** couplé à **HTML5/CSS3** pour le rendu visuel.

---

## 4. 🧰 Stack Technique

- **Langages :** Python 3, SQL, HTML5, CSS3
- **Framework & Backend :** Flask, Werkzeug WSGI
- **ORM & BDD :** SQLAlchemy, MySQL
- **Templating & Formulaires :** Jinja2, Flask-WTF
- **Authentification :** Flask-Login
- **Outils & IDE :** IntelliJ IDEA
- **Services Externes :** API REST Deezer

---

## 5. 📊 Bilan du Projet

Ce projet a permis de concevoir une application web complète, fonctionnelle et sécurisée en Python.

Le **défi technique majeur** a résidé dans la synchronisation fluide entre une base de données relationnelle locale et une API externe asynchrone. La mise en place de la logique d'"override" et du stockage différé (lazy saving) a permis de créer une plateforme légère, capable de proposer un catalogue musical quasi infini tout en conservant le contrôle administratif sur les données affichées.
