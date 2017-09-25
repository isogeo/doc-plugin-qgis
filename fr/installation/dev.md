# Utiliser la version en développement

A des fins de test.

## Utiliser la dernière version packagée ##

Méthode pour les utilisateurs expérimentés :

1. Télécharger la [dernière version du plugin](https://github.com/isogeo/isogeo-plugin-qgis/releases) ;
2. Décompresser dans `C:\Users\%USERNAME%\.qgis2\python\plugins` pour Windows ou `/home/$USER/.qgis2/python/plugins` pour Ubuntu ;

## Utiliser la version en développement ##

Méthode pour les développeurs :

Cloner le dépôt dans `C:\Users\%USERNAME%\.qgis2\python\plugins` pour Windows ou `/home/$USER/.qgis2/python/plugins` pour Ubuntu, en spécifiant un nom de dossier **sans caractères spéciaux ni tiret** (contrairement au nom du dépôt) :

```bash
cd C:\Users\%USERNAME%\.qgis2\python\plugins
git clone https://github.com/isogeo/isogeo-plugin-qgis.git isogeo_search_engine
```

Il est aussi possible de cloner le dépôt dans n'importe quel dossier et d'ajouter son chemin à la variable d'environnement `QGIS_PLUGINPATH`.





