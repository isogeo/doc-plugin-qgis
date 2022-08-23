---
description: Paramétrer les URLs interrogés par le plugin Isogeo pour QGIS
---

# Remplissage du fichier `config.json` {#configJSON}

> Cette rubrique concerne uniquement les utilisateur du plugin QGIS Isogeo dans un cadre _On-Premises_.

Au premier lancement du plugin, un fichier `config.json` est généré dans le répertoire d'installation du plugin (`C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` sous Windows et `/home/%userprofile%/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine` sous Ubuntu).

Ce fichier contient les 5 paramètres suivants :

* **api_base_url** : URL de base de l'API Isogeo, "https://v1.api.isogeo.com" en SaaS
* **api_auth_url** : URL d'authentification de l'API Isogeo, "https://id.api.isogeo.com" en SaaS
* **app_base_url** : URL de base de la platefrme d'administration Isogeo, "https://app.isogeo.com" en SaaS
* **help_base_url** : URL de base de l'aide en ligne Isogeo, "https://help.isogeo.com" en SaaS
* **background_map_url** : fond de carte utilisé dans l'onglet "Géographie" des [fiches de métadonnées](/usage/metadata#display), "type=xyz&format=image/png&styles=default&tileMatrixSet=250m&url=http://tile.openstreetmap.org/{z}/{x}/{y}.png" en SaaS

À sa création, ce fichier contient un paramétrage par défaut correspondant au mode SaaS :

```json
{
    "api_base_url": "https://v1.api.isogeo.com",
    "api_auth_url": "https://id.api.isogeo.com",
    "app_base_url": "https://app.isogeo.com",
    "help_base_url": "https://help.isogeo.com",
    "background_map_url": "type=xyz&format=image/png&styles=default&tileMatrixSet=250m&url=http://tile.openstreetmap.org/{z}/{x}/{y}.png"
}
```

Pour une utilisation du plugin QGIS Isogeo dans un cadre _On-Premises_, ce paramétrage doit être adapté à l'environnement de votre organisation :

* **api_base_url** : URL de base de l'API Isogeo hébergée dans votre environnement
* **api_auth_url** : URL d'authentification de l'API Isogeo hébergée dans votre environnement
* **app_base_url** : URL de base de la platefrme d'administration Isogeo hébergée dans votre environnement
* **help_base_url** : valeur par défaut à conserver si la machine de l'utilisateur du Plugin dispose d'une connexion Internet
* **background_map_url** : valeur par défaut à conserver si la machine de l'utilisateur du Plugin dispose d'une connexion Internet
