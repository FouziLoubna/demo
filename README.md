# demo
# Projet JDBC : Gestion des Sites

Ce projet JDBC développé avec NetBeans contient deux classes principales (`Site` et `Test`) qui permettent d'interagir avec une base de données MySQL pour gérer des informations sur des sites. Le projet permet d'ajouter des données dans une base de données et de les récupérer en utilisant JDBC.

## Description des Classes

### Classe `Site` :
La classe `Site` représente un modèle pour les données des sites. Elle contient les attributs suivants :
- `id` : l'identifiant unique du site (généré automatiquement dans la base de données).
- `nom` : le nom du site (exemple : "SAFI", "MARRAKECH", etc.).

Elle comporte aussi des méthodes getters et setters pour accéder et modifier ces attributs.

### Classe `Test` :
La classe `Test` contient deux méthodes principales :
- **`save(Site s)`** : Permet d'insérer un objet `Site` dans la base de données. Elle crée une connexion à la base de données, exécute une requête SQL d'insertion, et libère les ressources une fois la tâche terminée.
- **`load()`** : Permet de récupérer et d'afficher tous les enregistrements de la table `site` de la base de données. Elle exécute une requête `SELECT` et parcourt les résultats pour les afficher.

La méthode `main()` teste ces deux fonctionnalités en :
- Ajoutant trois sites à la base de données (`"SAFI"`, `"MARRAKECH"`, `"EL JADIDA"`).
- Récupérant et affichant ces sites.

## Fonctionnalités

- **Ajout de sites** : Insertion de nouveaux sites dans la base de données.
- **Récupération de sites** : Récupération de tous les sites enregistrés et affichage des résultats.

## Prérequis

Pour exécuter ce projet, vous aurez besoin des éléments suivants :
- **Java JDK** : Version 8 ou ultérieure.
- **NetBeans IDE** (ou un autre IDE compatible).
- **MySQL** : Une base de données MySQL active et une table appelée `site`.
- **Driver JDBC MySQL** : Assurez-vous d'avoir le driver JDBC MySQL (le fichier `mysql-connector-java.jar`) et de l'ajouter au classpath du projet.

## Configuration de la base de données

1. Créez une base de données dans MySQL appelée `db` (ou utilisez un autre nom que vous définirez dans l'URL de connexion).
2. Créez une table `site` avec la structure suivante :

   ```sql
   CREATE TABLE site (
       id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
       nom VARCHAR(50)
   );
