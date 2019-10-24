# Développement

Pour les développeurs ou à des fins de test, il est possible d'utiliser les versions au plus proche du développement. Les méthodes décrites ici sont destinées aux développeurs ou utilisateurs expérimentés.

## Utiliser la dernière version packagée

1. Télécharger la [dernière version du plugin](https://github.com/isogeo/isogeo-plugin-qgis/releases) ;
2. Décompresser dans `C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins` pour Windows ou `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins` pour Ubuntu.

## Utiliser une version en développement

* **version 1.x du plugin**

    Cloner le dépôt dans `C:\Users\%USERNAME%\.qgis2\python\plugins` pour Windows ou `/home/$USER/.qgis2/python/plugins` pour Ubuntu, en spécifiant un nom de dossier **sans caractères spéciaux ni tiret** (contrairement au nom du dépôt) :

    ```bash
    cd C:\Users\%USERNAME%\.qgis2\python\plugins
    git clone https://github.com/isogeo/isogeo-plugin-qgis.git isogeo_search_engine_dev --branch qgis2
    ```

* **version 3.x du plugin**

    Cloner le dépôt dans `C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins` pour Windows ou dans `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins` pour Ubuntu, en spécifiant un nom de dossier **sans caractères spéciaux ni tiret** (contrairement au nom du dépôt) :

    ```bash
    cd C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins
    git clone https://github.com/isogeo/isogeo-plugin-qgis.git isogeo_search_engine_dev
    ```

Il est aussi possible de cloner le dépôt dans n'importe quel dossier et d'ajouter son chemin à la variable d'environnement `QGIS_PLUGINPATH` (quelle que soit la version du plugin).
