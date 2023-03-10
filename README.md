# TP-Security

Description :
Implémentation d'une mini application d'authentification sécurisée

### Introduction

Le but du projet est de créer une mini application d'authentification sécurisée.

### Le travail réalisé :

- Restreindre l'utilisation de quelques caractères. spéciaux lors de la saisie des informations.spéciaux l'ors de la saisie des informations.
- L'obligation d'utiliser un mot de passe avec une taille supérieure à 8 caractères.
- Hasher le code avant de le sauvegarder dans la base de données.
- Vérifier si l'utilisateur est bien authentifié avant d'accéder au path qui le redirige vers son espace perso (http.../profile).
- Utilisation des sessions (le module passport de nodeJS) pour vérifier si l'utilisateur est bien authentifié durant la période de navigation.
- Afficher les erreurs de saisie sur le formulaire.
- Ajouter le boutton Logout pour déconnecter l'utilisateur.

### Téchnologies

- Installation de Vue.js.
- Installation de Node.js.
- Installation de la Base de données MySql.

### Lancement du serveur :

- Aller dans le dossier ./server.
- Installer les packages :

```
npm i
```

- Configuration de la base de données :<br>
  Dans la ligne de commande Sql lancez les commandes suivantes :

```
# Création de l'utilisateur "tp_user". Si vous changez le mot de passe il faut le changer aussi dans le fichier d'environnement './server/.env'
CREATE USER tp_user  WITH ENCRYPTED PASSWORD 'XXXXX';

# Création de la base de données "tp_user"
CREATE DATABASE tp_database;

# Accéder à la base de données crée
\c tp_database

# Attribuer les permissions au nouvel utilisateur.
GRANT ALL PRIVILEGES ON DATABASE tp_database  TO tp_user ;

# Création de la table "users"
CREATE TABLE users
(id BIGSERIAL PRIMARY KEY NOT NULL,
 name VARCHAR(200) NOT NULL,
 email VARCHAR(200) NOT NULL,
 password VARCHAR(200) NOT NULL,
 UNIQUE (email)
);

# Créer un utilisateur (Facultatif) juste pour le test
INSERT INTO users  (name,email,password)
VALUES ('userName','userEmail','userPassword');

```

- Lancer le serveur (dans le dossier './server')

```
npm run start
```

### Lancement du client :

- Aller dans le dossier './vue-3-crud'
- Installer les packages :

```
npm i
```

- Lancer le client :

```
npm run serve
```

- Le client devrait être lancer en local, sur l'adresse : [http://localhost:8080/login](http://localhost:8080/login).
