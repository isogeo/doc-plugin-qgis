---
description: Intégration du portail Isogeo à l'utilisation du plugin Isogeo pour QGIS 
---

# Ajouter l'URL de la metadonnée du Portail Isogeo aux propriétés de la couche {#metadata_portal_url}

> Cette rubrique concerne uniquement les utilisateurs du plugin QGIS ayant également accès au [Portail Isogeo](https://www.isogeo.com/nos-produits/Portail).

Cette fonctionnalité implique deux prérequis :

* certains des catalogues partagés au plugin QGIS le sont également au Portail Isogeo
* certaines des fiches de métadonnées partagées remplissent les conditions permettant l'ajout de couches au canevas:
  * [données fichier](/usage/display.md#add_files)
  * [tables PostGIS ou Oracle Spatial](/usage/display.md#add_tables)
  * [couches de services géographiques](/usage/display.md#add_services)

Si ces 2 prérequis sont satisfaits, l'URL de la fiche de métadonnées du Portail Isogeo correspondant à la couche ajoutée au canevas sera affichable dans les "Propriétés" de cette couche (dans le champ "Url de la donnée" de la rubrique "Description" de l'onglet "QGIS Server") :

![Propriétés de la couche, onglet "QGIS Server"](/assets/layer_properties_portal_data_url_fr.png)

Afin d'obtenir ce résultat, il faut passer par une courte étape de configuration.

![](/assets/layer_properties_portal_data_url_open_dialog_btn.png)

La boîte de dialogue (ci-dessous) est accessible en cliquant sur un bouton situé dans la rubrique "Ajout de couche" de l'onglet "Paramètres" (ci-dessus).

![](/assets/layer_properties_portal_data_url_dialog.png)

Avant d'ajouter l'URL de la metadonnée du Portail Isogeo aux propriétés de la couche, le plugin doit générer cet URL. Pour ce faire, il se base sur la valeur indiquée dans la zone de saisie de texte.

![](/assets/layer_properties_portal_data_url_dialog_input.png)

Une fois généré, l'URL est ajouté aux propriétés des couches ajoutées uniquement si la case "Ajouter l'URL de la métadonnée du portail Isogeo..." est cochée.

![](/assets/layer_properties_portal_data_url_dialog_chb.png)

> La [recherche](/usage/search.md#reset) doit être réinitialisée pour prendre en compte les modifications effectuées dans la boîte de dialogue "Configuration de l'ajout de l'URL du portail".
