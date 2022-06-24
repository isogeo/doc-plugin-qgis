---
description: Ajouter une donnée à la carte de QGIS (canevas) avec le plugin Isogeo
---

# Ajouter une donnée à la carte {#add_data_from_metadata}

La principale finalité du plugin est de permettre à l'utilisateur final d'ajouter les données du catalogue directement à sa carte, sans se soucier de configurer les paramètres d'accès aux données sources.

## Fonctionnement

Pour pouvoir ajouter les données à l'espace de travail du logiciel SIG, le plugin se base uniquement sur les métadonnées. Pour rappel :

* **aucune donnée ne transite par notre infrastructure**
* seules les métadonnées sont utilisées et plus particulièrement les champs d'identification de la donnée source ([emplacement](https://help.isogeo.com/admin/fr/features/documentation/md_identification.html#path) et [nom technique](https://help.isogeo.com/admin/fr/features/documentation/md_identification.html#name))

La quatrième colonne du tableau des résultats de recherche liste les options d'ajout possibles.

Il y a plusieurs cas de figure :

* La donnée peut être ajoutée d'une seule manière. Auquel cas, la colonne "Ajouter" ne comprend qu'un bouton. Au clic, la donnée sera ajoutée à la carte.

![Donn&eacute;e ajoutable d&apos;une seule mani&egrave;re](/assets/search_results_addOk_one_fr.png)

* La donnée peut être ajoutée de plusieurs manières différentes. Auquel cas, la colonne "Ajouter" comprend une liste déroulante permettant à l'utilisateur de choisir entre les différentes options.

![Donnée ajoutable de plusieurs manières](/assets/search_results_add_OK_multi_fr.png)

* La donnée ne peut pas être ajoutée : le fichier n'est pas disponible et il n'y a pas de services renseignés (ou ceux-ci sont mal renseignés).

![Donnée non ajoutable - Critères non remplis](/assets/search_results_addNot_fr.png)

---

## Données fichier {#add_files}

Le chemin vers la donnée doit être rempli dans le champ `Emplacement de la donnée` de l'onglet `Identification` sur [https://app.isogeo.com](https://app.isogeo.com). Ce chemin doit être accessible :

* par l'utilisateur ayant lancé QGIS \(droits en lecture\);
* depuis le poste sur lequel le plugin se trouve \(en local ou via le réseau local\).

### Cache {#filespaths_cache}

Pour améliorer les performances, le plugin intègre un système de cache minimaliste sur les chemins d'accès inaccessibles. Pour vider le cache, cliquer sur le bouton dédié dans l'onglet paramètres :

![Bouton pour vider le cache des chemins de fichiers inacessibles](/assets/settings_cache_trash_fr.png)

### Formats supportés

* Vecteur
  * DXF
  * DGN
  * Esri shapefile
  * MapInfo tab
* Raster
  * ECW
  * Esri ascii grid
  * Geotiff
  * Intergraph gdb
  * JPEG
  * PNG
  * XYZ

---

## Tables PostGIS ou Oracle Spatial {#add_tables}

Une table PostGIS ou Oracle Spatial pourra être ajoutée via le plugin dans les conditions suivantes :

* La fiche documentant la table a été **créée à partir du [Scan FME Isogeo](https://help.isogeo.com/scan/fr/index.html)**.
* La **connexion à la base de données** dans laquelle elle se trouve a été configurée au choix :
  * dans le **gestionnaire des sources de données** de QGIS;
  * dans le **fichier `_user/db_connections.json`**.

  > Si plusieurs connexions ont été configurées pour des bases de données dont le nom est identique, il est possible d'[indiquer au plugin la connexion a utiliser](/usage/configuration.md#db_connections) pour accéder aux données stockées dans la base concernée.

### Connexion configurée dans le gestionnaire des sources de données de QGIS {#add_tables_from_QGISconnection}

En indiquant mot de passe et nom d'utilisateur et en choisissant de les stocker (pour les bases de donées Oracle et PostGIS):

![Configuration 'traditionnelle' d'une connexion à une base de données](/assets/display_postgis_dbconnection_tradi.png)

>Pour les **bases de données PostgreSQL uniquement**, il est possible d'indiquer le **nom d'un service** dans le gestionnaire des sources de données. Ce "service" doit avoir été spécifié dans une fichier de configuration [`pg_service.conf`](https://www.postgresql.org/docs/14/libpq-pgservice.html) dont l'emplacement est enregistré dans une variable d'environnement "PGSERVICEFILE" configurée dans l'OS et dans QGIS (Menu "Préférences" > "Options..." > onglet "Système" > Rubrique "Environnement" > bouton "+") :
>![Configuration d'une connexion à une base de données PostgreSQL via un Service](/assets/display_postgis_dbconnection_service.png)

### Connexion configurée dans le fichier `_user/db_connections.json` {#add_tables_from_fileconnection}

En inscrivant les informations de connexion **dans le fichier `_user/db_connections.json`** qui se trouve dans le répertoire d'installation du plugin QGIS Isogeo (`C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` dans la plupart des cas).

Par exemple pour configurer une seule connexion à une base de données PostgreSQL :

```json
{
    "Oracle" : [],
    "PostgreSQL" : [
        {
            "connection_name" : "Nom de la connexion (il doit être unique)",
            "host" : "hôte",
            "port" : "port", 
            "database" : "nom de la base de données",
            "username" : "nom d'utilisateur",
            "password" : "mot de passe de l'utilisateur"
        }
    ]
}
```

Autre exemple, pour configurer 2 connexions à des bases de données PostgreSQL et 1 connexion à une base de données Oracle :

```json
{
    "Oracle" : [
        {
            "connection_name" : "Nom de la connexion (il doit être unique)",
            "host" : "hôte",
            "port" : "port", 
            "database" : "nom de la base de données",
            "username" : "nom d'utilisateur",
            "password" : "mot de passe de l'utilisateur"
        }
    ],
    "PostgreSQL" : [
        {
            "connection_name" : "Nom de la connexion (il doit être unique)",
            "host" : "hôte",
            "port" : "port", 
            "database" : "nom de la base de données",
            "username" : "nom d'utilisateur",
            "password" : "mot de passe de l'utilisateur"
        },
        {
            "connection_name" : "Nom de la connexion (il doit être unique)",
            "host" : "hôte",
            "port" : "port", 
            "database" : "nom de la base de données",
            "username" : "nom d'utilisateur",
            "password" : "mot de passe de l'utilisateur"
        }
    ]
}
```

Dans le cas des bases de données Oracle, il est parfois nécessaire de rajouter une entrée `database_alias`. Lorsque la valeur du [champ "Emplacement de la ressource"](https://help.isogeo.com/admin/fr/features/documentation/md_identification.html#path) des fiches de métadonnées est différente du nom de la base de données, il faut renseigner l'entrée `database_alias` en inscrivant la valeur du champ "Emplacement de la ressource".

```json
{
    "Oracle" : [
        {
            "connection_name" : "Nom de la connexion (il doit être unique)",
            "host" : "hôte",
            "port" : "port", 
            "database" : "nom de la base de données",
            "database_alias" : "emplacement de la ressource",
            "username" : "nom d'utilisateur",
            "password" : "mot de passe de l'utilisateur"
        }
    ],
    "PostgreSQL" : []
}
```

> Si cette option semble ne pas fonctionner, prenez le temps de vérifier que le fichier a été rempli avec des informations valides. Vous pouvez également utiliser [ce site](https://jsonformatter.curiousconcept.com/#) (ou un équivalent) pour vérifier que le contenu du fichier JSON est conforme aux spécifications.

---

## Services géographiques {#add_services}

Le plugin supporte les couches de services documentés automatiquement et associés aux métadonnées de données.

> **Note importante**  
> Seuls les services "ouverts" (ne nécessitant pas d'authentification) sont exploitables via le plugin QGIS Isogeo.

Consulter [l'aide en ligne au sujet du recensement automatisé des services et de l'association couche de service / donnée cataloguée](https://help.isogeo.com/admin/fr/features/inventory/md_services/srv_intro.html).

Il supporte également les URLs de couches de services renseignées manuellement dans la métadonnée. Si cette méthode \(dépréciée\) est utilisée :

* L’url doit contenir la base de l’url du service géographique
* Elle doit également contenir le nom de la couche du service à afficher.

Consulter [l'aide en ligne sur les syntaxes de documentation manuelle des couches de services](https://help.isogeo.com/admin/fr/features/publish/webservices.html).

### Formats de services supportés

* Esri Feature Service (EFS)
* Esri Map Service (EMS)
* Web Feature Service (WFS)
* Web Map Service (WMS)
* Web Map Tile Service (WMTS)

> **Note importante**  
> Si le titre de la couche comprend des caractères spéciaux ou des accents, il est possible que la couche ne puisse pas être affichée convenablement dans QGIS. Il s’agit d’un problème de gestion de l'encodage par l’API PyQGIS.
