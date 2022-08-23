---
description: Configuration des connections aux bases de données Oracle et PostgreSQL dans le plugin Isogeo pour QGIS
---

# Configuration des connexions aux bases de données (Oracle et PostgreSQL) utilisées par le plugin

> Toute cette rubrique s'appuie sur l'exemple des bases de données PostgreSQL mais le fonctionnement est identique pour les bases de données Oracle.

## Contexte

Cette fonctionnalité sert à gérer le cas suivant : plusieurs connexions ont été configurées dans QGIS pour des bases de données dont le nom est identique (champ "Base de données" du formulaire de configuraton de la connexion).

Cette situation peut survenir dans les cas suivants :

* on cherche à se connecter à une même base de données avec différents utilisateurs :
![](/assets/config_pgdb_connection_diff_user.png)
* il s'agit de deux bases de données dont le nom est identique mais qui sont hébergées sur des serveurs différents :
![](/assets/config_pgdb_connection_diff_host.png)

## Comportement par défaut du plugin {#db_connections_default}

Dans ce contexte, le plugin QGIS propose à l'utilisateur une option d'ajout par connexion enregistrée en précisant le nom de la connexion :

![](/assets/config_pgdb_connection_several_options.png)

De cette manière, l'utilisateur peut choisir lui-même, au moment d'ajouter la couche, la connexion qui sera utilisées pour accéder à la table correspondante.

## Paramétrage des connexions utilisées par le plugin QGIS {#db_connections_config}

Afin d'éviter d'avoir à choisir la connexion à chaque ajout de couche, il est possible de configurer ce choix de manière durable.

![](/assets/config_db_connection_open_dialog_btn.png)

Une interface graphique dédiée (ci-dessous) est accessible en cliquant sur un bouton situé dans la rubrique "Ajout de couche" de l'onglet "Paramètres" du plugin (ci-dessus, bouton de gauche pour les connexions Oracle et bouton de droite pour les connections PostgreSQL).

![](/assets/config_pgdb_connection_dialog.png)

Les listes déroulantes (colonne de droite) permettent de sélectionner la connexion qui sera utilisée par le plugin pour accéder à la base de données correspondante (colonne de gauche).

![](/assets/config_pgdb_connection_dialog_cbb_open.png)

Une fois la configuration effectuée, l'utilisateur peut :

1. **Réinitialiser** le tableau : pour remettre les listes déroulantes dans leur configuration initiale (au moment de l'ouverture de la boîte de dialogue)
2. **Enregistrer** la configuration : pour enregistrer durablement les choix faits par l'utilisateur avant de fermer la boîte de dialogue
3. **Annuler** la configuration : pour fermer la boîte de dialogue sans prendre en compte les choix faits par l'utilisateur

![](/assets/config_pgdb_connection_dialog_btn_box.png)

Si une connexion à une base de données a été modifiée/ajoutée/supprimée pendant la session d'utilisation courante de QGIS (dans le gestionnaire des sources de données ou dans le fichier `_user/db_connections.json`), il faut cliquer sur "Recharger les connexions" pour que la modification soit prise en compte par le plugin Isogeo :

![](/assets/config_pgdb_connection_dialog_reload_conn.png)

Une fois la configuration enregistrée, elle se répercute dans les options d'ajout de couche proposées à l'utilisateur :

![](/assets/config_pgdb_connection_unique_option.png)

Le plugin ne propose plus qu'une option d'ajout à l'utilisateur, correspondant à la connexion qu'il a sélectionné.

> La [recherche](/usage/search.md#reset) doit être réinitialisée pour prendre en compte cette configuration.