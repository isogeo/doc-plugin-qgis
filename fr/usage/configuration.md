# Configuration et paramètres

## Changer les clés d'authentification {#authentication}

Dans les paramètres, il est également possible de changer de compte, pour se connecter à une autre instance du plugin QGIS.

![Changer les clés API du plugin](/assets/settings_switch_api_fr.png)

---

## Partager les catalogues de ses métadonnées au plugin {#shares}

[Créer un partage](http://help.isogeo.com/admin/fr/features/admin/shares.html) avec un ou plusieurs catalogues vers l'application _Plugin QGIS_ dans l'administration des partages sur [APP](https://app.isogeo.com) ;

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

## Ajouter l'URL de la metadonnées du Portail Isogeo aux propriétés de la couche {#metadata_portal_url}

> Cette rubrique concerne uniquement les utilisateurs du plugin QGIS ayant également accès au [Portail Isogeo](https://www.isogeo.com/nos-produits/Portail)

Cette fonctionnalité nécessite deux prérequis :

* certains des catalogues partagés au plugin QGIS le sont également au Portail Isogeo
* certaines des fiches de métadonnées partagées remplissent [les conditions permettant l'ajout de couches au canevas](/usage/display.md#add_criteria)

Si ces conditions sont remplies, l'URL de la fiche de métadonnées du Portail Isogeo correspondant à la couche ajoutée au canevas apparaîtra dans les "Propriétés" de cette couche (dans le champ "Url de la donnée" de la rubrique "Description" de l'onglet "QGIS Server") :

![Propriétés de la couche, onglet "QGIS Server"](/assets/layer_properties_portal_data_url_fr.png)

Afin d'obtenir ce résultat, il est nécessaire de cocher la case correspondante dans l'onglet "Paramètres" du plugin et d'indiquer dans le champ de texte prévu à cet effet la base de l'URL du portail comme ci-dessous :

![Paramètres du Portail isogeo](/assets/settings_isogeo_portal_fr.png)