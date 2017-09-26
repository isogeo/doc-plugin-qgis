# Support et questions fréquentes

## Comment signaler un comportement anormal ?

Si vous obtenez un message d'erreur ou bien vous constatez un comportement anormal, voici la procédure à suivre :

  - vérifier dans cette documentation si par hasard rien ne correspond à une explication du comportement constaté ;)
  - regarder l'onglet dédié à isogeo dans la fenêtre des messages de QGIS :

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/qgis_log_view_tab_isogeo_fr.png "Ouvrir la fenêtre des messages de QGIS")

Le problème persiste et signe ? Le (dys)fonctionnement est incompréhensible ?

Il faut alors [créer un ticket ici](https://github.com/isogeo/isogeo-plugin-qgis/issues) en joignant une capture de l'onglet de la fenêtre messages et *surtout le fichier log_isogeo_plugin.log* situé dans le dossier d'installation du plugin (`C:\Users\%USERNAME%\.qgis2\python\plugins` pour Windows ou `/home/$USER/.qgis2/python/plugins` pour Debian) :

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/qgis_plugin_folder_structure.png "Structure du dossier du plugin Isogeo pour QGIS")
___

## Questions fréquentes

### Pourquoi n'y a t'il aucune donnée dans mon plugin ?

Vérifier qu'au moins un partage alimente l'application : voir [comment partager à l'application depuis Isogeo](/usage/configuration.md).

### Pourquoi aucun résultat n'est ajoutable ?

Pour qu'une donnée soit ajoutable à la carte (canevas cartographique selon le vocabulaire QGIS), il faut que des informations le permettant soient cataloguées dans la métadonnée. 

Pour en savoir plus, [consulter la section dédiée dans la documentation](/usage/display.md).

### Pourquoi mon service WMS ne s'affiche pas alors que sa légende est bien présente ?

Il peut y avoir plusieurs raisons :

- le service WMS n'est pas conforme aux exigences de QGIS ;
- des caractères spéciaux sont présents dans certains des intitulés (titre, étiquettes légende...) et l'encodage n'est pas conforme ;
- le style par défaut de la couche du WMS contient une anomalie ;

### L'ajout de donnée prend-il en compte les fichiers de symbologie (.qlr) ?

Oui, si le qlr se nomme de la même façon que le fichier de la donnée source et est situé dans le même dossier.






