---
description: Ajouter une donnée à la carte de QGIS (canevas) avec le plugin Isogeo
---

# Ajouter une donnée à la carte {#add_data_from_metadata}

La principale finalité du plugin est de permettre à l'utilisateur final d'ajouter les données du catalogue directement à sa carte, sans se soucier de configurer les paramètres d'accès aux données sources.

## Fonctionnement

Pour pouvoir ajouter les données à l'espace de travail du logiciel SIG, le plugin se base uniquement sur les métadonnées. Pour rappel :

* **aucune donnée ne transite par notre infrastructure**
* seules les métadonnées sont utilisées et plus particulièrement les champs d'identification de la donnée source ([emplacement et nom technique](https://help.isogeo.com/admin/fr/features/documentation/md_identification.html#emplacement--nom-de-la-donn%C3%A9e))

## Options d&apos;ajout {#add_options}

Pour ajouter une donnée à la carte, la colonne "Ajouter" liste les options possibles.

Il y a plusieurs cas de figure :

* La donnée peut être ajoutée d'une seule manière. Auquel cas, la colonne "Ajouter" ne comprend qu'un bouton. Au clic, la donnée sera ajoutée à la carte.

![Donn&eacute;e ajoutable d&apos;une seule mani&egrave;re](/assets/search_results_addOk_one_fr.png)

* La donnée peut être ajoutée de plusieurs manières différentes. Auquel cas, la colonne "Ajouter" comprend une liste déroulante permettant à l'utilisateur de choisir entre les différentes options.

![Donnée ajoutable de plusieurs manières](/assets/search_results_add_OK_multi_fr.png)

* La donnée ne peut pas être ajoutée : le fichier n'est pas disponible et il n'y a pas de services renseignés \(ou ceux-ci sont mal renseignés\).

![Donnée non ajoutable - Critères non remplis](/assets/search_results_addNot_fr.png)

---

## Critères {#add_criteria}

### Données fichier {#add_files}

Le chemin vers la donnée doit être rempli dans le champ `Emplacement de la donnée` de l'onglet `Identification` sur [https://app.isogeo.com](https://app.isogeo.com). Ce chemin doit être accessible :

* par l'utilisateur ayant lancé QGIS \(droits en lecture\);
* depuis le poste sur lequel le plugin se trouve \(en local ou via le réseau local\).

#### Cache {#filespaths_cache}

Pour améliorer les performances, le plugin intègre un système de cache minimaliste sur les chemins d'accès inaccessibles. Pour vider le cache, cliquer sur le bouton dédié dans l'onglet paramètres :

![Bouton pour vider le cache des chemins de fichiers inacessibles](/assets/settings_cache_trash_fr.png)

#### Formats supportés

##### Vecteur

* DXF
* DGN
* Esri FileGDB
* Esri shapefile
* MapInfo tab

##### Raster

* ECW
* Esri ascii grid
* Geotiff
* Intergraph gdb
* JPEG
* PNG
* XYZ

### Données PostGIS ou Oracle Spatial {#add_tables}

Une table PostGIS ou Oracle Spatial pourra être ajoutée via le plugin dans les conditions suivantes :

* La fiche documentant la table a été **créée à partir du Scan FME** Isogeo. En créant une fiche manuellement dans [https://app.isogeo.com](https://app.isogeo.com), il est impossible de renseigner le champ _name_ nécessaire à l’ajout de la table.
* La **connexion à la base de données** dans laquelle elle se trouve a été configurée au choix :
  * **dans le gestionnaire des sources de données de QGIS**, en indiquant mot de passe et nom d'utilisateur et en choisissant de les stocker :
  !["Configuration 'traditionnelle' d'une connexion à une base de données"](/assets/display_postgis_dbconnection_tradi.png)
  * en inscrivant les informations de connexion **dans le fichier `_user/db_connections.json`** qui se trouve dans le répertoire d'installation du plugin QGIS Isogeo (`C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` dans la plupart des cas) :

    Par exemple pour configurer une seule connexion à une base de données PostgreSQL :

    ```json
    {
        "Oracle" : [],
        "PostgreSQL" : [
            {
                "connection_name" : "Isogeo interne - lecture seule",
                "host" : "XX.X.XXX.XX",
                "port" : "5432", 
                "database" : "isogeo",
                "username" : "isogeo_reader",
                "password" : "mot_de_passe"
            }
        ]
    }
    ```

    De la même manière, pour configurer 2 connexions à une base de données PostgreSQL et 1 connexion à une base de données Oracle :

    ```json
    {
        "Oracle" : [
            {
                "connection_name" : "Isogeo interne - Oracle Spatial démonstration",
                "host" : "XX.X.XXX.XX",
                "port" : "5432", 
                "database" : "isoora",
                "username" : "isogeo_spatial_demo",
                "password" : "mot_de_passe"
            }
        ],
        "PostgreSQL" : [
            {
                "connection_name" : "Isogeo interne - lecture seule",
                "host" : "XX.X.XXX.XX",
                "port" : "5432", 
                "database" : "isogeo",
                "username" : "isogeo_reader",
                "password" : "mot_de_passe"
            },
            {
                "connection_name" : "Isogeo interne - lecture et écriture",
                "host" : "XX.X.XXX.XX",
                "port" : "5432", 
                "database" : "isogeo",
                "username" : "isogeo_writer",
                "password" : "mot_de_passe"
            }
        ]
    }
    ```

    > Si cette option semble ne pas fonctionner, prenez le temps de vérifier que chacun des 6 champs a bien été rempli. Vous pouvez également utiliser [ce site](https://jsonformatter.curiousconcept.com/#) (ou un équivalent) pour vérifier que le format du contenu du fichier JSON est conforme aux spécifications.

  * pour les bases de données **PostgreSQL uniquement**, il existe une dernière option : en indiquant le **nom d'un service** dans le gestionnaire des sources de données. Ce "service" doit avoir été spécifié dans une fichier de configuration [`pg_service.conf`](https://www.postgresql.org/docs/14/libpq-pgservice.html) dont l'emplacement est enregistré dans une variable d'environnement "PGSERVICEFILE" configurée dans l'OS et dans QGIS (Menu "Préférences" > "Options..." > onglet "Système" > Rubrique "Environnement" > bouton "+") :

    !["Configuration d'une connexion à une base de données PostgreSQL via un Service"](/assets/display_postgis_dbconnection_service.png)

> Dans le cas où plusieurs connexions ont été configurées pour des bases de données dont le nom est identique, il faudra [indiquer au plugin la connexion a utiliser](/usage/configuration.md#db_connections) pour accéder aux données stockées dans la base concernée.

### Services géographiques {#add_services}

Le plugin supporte les couches de services documentés automatiquement et associés aux métadonnées de données.

> **Note importante**  
> Seuls les services "ouverts" (ne nécessitant pas d'authentification) sont exploitables via le plugin QGIS Isogeo.

Consulter [l'aide en ligne au sujet du recensement automatisé des services et de l'association couche de service / donnée cataloguée](https://help.isogeo.com/admin/fr/features/inventory/md_services/srv_intro.html).

Il supporte également les URLs de couches de services renseignées manuellement dans la métadonnée. Si cette méthode \(dépréciée\) est utilisée :

* L’url doit contenir la base de l’url du service géographique
* Elle doit également contenir le nom de la couche du service à afficher.

Consulter [l'aide en ligne sur les syntaxes de documentation manuelle des couches de services](https://help.isogeo.com/admin/fr/features/publish/webservices.html).

#### Formats de services supportés

* Esri Feature Service \(EFS\)
* Esri Map Service \(EMS\)
* Web Feature Service \(WFS\)
* Web Map Service \(WMS\)
* Web Map Tile Service \(WMTS\)

> **Note importante**  
> Si le titre de la couche comprend des caractères spéciaux ou des accents, il est possible que la couche ne puisse pas être affichée convenablement dans QGIS. Il s’agit d’un problème de gestion de l'encodage par l’API PyQGIS.
