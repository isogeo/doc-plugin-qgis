# Ajouter une donnée à la carte de QGIS

Pour ajouter une donnée à la carte, la colonne "Ajouter" liste les options possibles.

Il y a plusieurs cas de figure :

- La donnée ne peut pas être ajoutée : le fichier n'est pas disponible et il n'y a pas de services renseignés (ou ceux-ci sont mal renseignés).

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_results_addNot_fr.png "TODO")

- La donnée peut être ajoutée d'une seule manière. Auquel cas, la colonne "Ajouter" ne comprend qu'un bouton. Au clic, la donnée sera ajoutée à la carte.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_results_addOk_one_fr.png "TODO")

- La donnée peut être ajoutée de plusieurs manières différentes. Auquel cas, la colonne "Ajouter" comprend une liste déroulante permettant à l'utilisateur de choisir entre les différentes options.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_results_add_OK_multi_fr.png "TODO")

## Critères pour qu'une donnée soit ajoutable

### Formats supportés

#### Fichiers au format vecteur 

- DXF
- DGN
- Esri FileGDB
- Esri shapefile
- MapInfo tab

#### Fichiers au format raster

- ECW
- Esri ascii grid
- Geotiff
- Intergraph gdb
- JPEG
- PNG
- XYZ

#### Données stockées en base de données

- Tables PostGIS

#### Services géographiques

- Web Feature Service (WFS)
- Web Map Service (WMS)
- Web Map Tile Service (WMTS)

### Autres conditions

#### Conditions pour ajouter une table PostGIS

Une table PostGIS pourra être ajoutée par le plugin dans les conditions suivantes : 

- La connexion à la base de données dans laquelle elle se trouve a été enregistrée dans QGIS
- L’option “Enregistrer le nom d’utilisateur et le mot de passe” a été choisie
- La fiche documentant la table PostGIS a été créée à partir du scan FME Isogeo. En créant une fiche manuellement dans https://app.isogeo.com, il est impossible de renseigner le champ *name* nécessaire à l’ajout de la table.

#### Conditions pour ajouter une donnée fichier

Le chemin vers la donnée doit être rempli dans le champ *Emplacement de la donnée* sur https://app.isogeo.com. 
Ce chemin doit être accessible :
* par l'utilisateur ayant lancé QGIS (droits en lecture);
* depuis le poste sur lequel le plugin se trouve (en local ou via le réseau local).

#### Conditions pour ajouter une donnée via un service géographique

Le plugin supporte les couches de services documentés automatiquement et associés aux métadonnées de données.  

Consulter [l'aide en ligne au sujet du recensement automatisé des services et de l'association couche de service / donnée cataloguée](http://help.isogeo.com/fr/features/inventory/md_services/srv_intro.html).

Il supporte également les URLs de couches de services renseignées manuellement dans la métadonnée. Si cette méthode (dépréciée) est utilisée :
- L’url doit contenir la base de l’url du service géographique
- Elle doit également contenir le nom de la couche du service à afficher.

Consulter [l'aide en ligne sur les syntaxes de documentation manuelle des couches de services](http://help.isogeo.com/fr/features/publish/webservices.html).

##### Note importante : 

Si le titre de la couche comprend des caractères spéciaux ou des accents, il est possible que la couche ne puisse pas être affichée convenablement dans QGIS. Il s’agit d’un problème de gestion de l'encodage par l’API PyQGIS.
