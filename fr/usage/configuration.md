---
description: Configurer le plugin Isogeo pour QGIS
---

# Configuration et paramètres

## Changer les clés d'authentification {#authentication}

Dans les paramètres, il est également possible de changer de compte, pour se connecter à une autre instance du plugin QGIS.

![Changer les clés API du plugin](/assets/settings_switch_api_fr.png)

---

## Partager les catalogues de ses métadonnées au plugin {#shares}

[Créer un partage](https://help.isogeo.com/admin/fr/features/admin/shares.html) avec un ou plusieurs catalogues vers l'application _Plugin QGIS_ dans l'administration des partages sur [APP](https://app.isogeo.com) ;

![Créer et configurer un partage](/assets/app_share_toPlugin_fr.png)

---

## Consulter les groupes de travail alimentant le plugin {#app_properties}

Dans l'onglet "Paramètres" du plugin, on retrouve les informations sur les partages qui alimentent l'application.

![Informations sur les partages dans les Paramètres](/assets/settings_shares_details_fr.png)

On retrouve donc :

* le nom de l'application déclarée dans Isogeo qui correspond au plugin ;
* le nombre de partages qui l'alimentent. On trouve ensuite les informations sur chaque partage :
  * le nom du partage ;
  * la date de dernière mise à jour du partage ;
  * le groupe de travail Isogeo à qui appartient le partage, ainsi que le mail de contact

---

## Configuration des connexions PostgeSQL utilisées par le plugin {#pgdb_connections}

### Contexte

Cette fonctionnalité sert à gérer le cas suivant : plusieurs connexions PostgeSQL ont été configurées dans QGIS pour des bases de données dont le nom est identique (champ "Base de données" du formulaire de configuraton de la connexion).

Cette situation peut survenir dans les cas suivants :

* on cherche à se connecter à une même base de données avec différents utilisateurs :
![](/assets/config_pgdb_connection_diff_user.png)
* il s'agit de deux bases de données dont le nom est identique mais qui sont hébergées sur des serveurs différents :
![](/assets/config_pgdb_connection_diff_host.png)

### Comportement par défaut du plugin {#pgdb_connections_default}

Dans ce contexte, le plugin QGIS propose à l'utilisateur une option d'ajout par connexion enregistrée en précisant le nom de la connexion :

![](/assets/config_pgdb_connection_several_options.png)

De cette manière, l'utilisateur peut choisir lui-même, au moment d'ajouter la couche, la connexion qui sera utilisées pour accéder à la table PostGIS correspondante.

### Paramétrage des connexions utilisées par le plugin QGIS {#pgdb_connections_config}

Afin d'éviter d'avoir à choisir la connexion à chaque ajout de couche, il est possible de configurer ce choix de manière durable.

![](/assets/config_pgdb_connection_open_dialog_btn.png)

Une interface graphique dédiée (ci-dessous) est accessible en cliquant sur un bouton situé dans la rubrique "Paramètres d'ajout de couche" de l'onglet "Paramètres" du plugin (ci-dessus).

![](/assets/config_pgdb_connection_dialog.png)

Les listes déroulantes (colonne de droite) permettent de sélectionner la connexion qui sera utilisée par le plugin pour accéder à la base de données correspondante (colonne de gauche).

![](/assets/config_pgdb_connection_dialog_cbb_open.png)

Une fois la configuration effectuée, l'utilisateur peut :

1. **Réinitialiser** le tableau : pour remettre les listes déroulantes dans leur configuration initiale (au moment de l'ouverture de la boîte de dialogue)
2. **Enregistrer** la configuration : pour enregistrer durablement les choix faits par l'utilisateur avant de fermer la boîte de dialogue
3. **Annuler** la configuration : pour fermer la boîte de dialogue sans prendre en compte les choix faits par l'utilisateur

![](/assets/config_pgdb_connection_dialog_btn_box.png)

Si une connexion à une base de données a été modifiée/ajoutée/supprimée pendant la session d'utilisation courante de QGIS, il faut cliquer sur "Recharger les connexions" pour que la modification soit prise en compte par le plugin Isogeo :

![](/assets/config_pgdb_connection_dialog_reload_conn.png)

Une fois la configuration enregistrée, elle se répercute dans les options d'ajout de couche proposées à l'utilisateur :

![](/assets/config_pgdb_connection_unique_option.png)

Le plugin ne propose plus qu'une option d'ajout à l'utilisateur, correspondant à la connexion qu'il a sélectionné.

> La [recherche](/usage/search.md#reset) doit être réinitialisée pour prendre en compte cette configuration.

---

## Ajouter l'URL de la metadonnée du Portail Isogeo aux propriétés de la couche {#metadata_portal_url}

> Cette rubrique concerne uniquement les utilisateurs du plugin QGIS ayant également accès au [Portail Isogeo](https://www.isogeo.com/nos-produits/Portail).

Cette fonctionnalité implique deux prérequis :

* certains des catalogues partagés au plugin QGIS le sont également au Portail Isogeo
* certaines des fiches de métadonnées partagées remplissent [les conditions permettant l'ajout de couches au canevas](/usage/display.md#add_criteria)

Si ces 2 prérequis sont satisfaits, l'URL de la fiche de métadonnées du Portail Isogeo correspondant à la couche ajoutée au canevas apparaîtra dans les "Propriétés" de cette couche (dans le champ "Url de la donnée" de la rubrique "Description" de l'onglet "QGIS Server") :

![Propriétés de la couche, onglet "QGIS Server"](/assets/layer_properties_portal_data_url_fr.png)

Afin d'obtenir ce résultat, il est nécessaire de cocher la case correspondante dans l'onglet "Paramètres" du plugin et d'indiquer dans le champ de texte prévu à cet effet la base de l'URL du Portail comme ci-dessous :

![Paramètres du Portail isogeo](/assets/settings_isogeo_portal_fr.png)

> La [recherche](/usage/search.md#reset) doit être réinitialisée pour prendre en compte les modifications apportées au champ ci-dessus.
