# Rechercher

## Rechercher

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/ui_tabs_main_search_empty_fr.png "Interface avec recherche vide")

### Recherche sémantique

La recherche textuelle s'effectue dans la barre de saisie de texte en haut à gauche de la fenêtre du plugin. 

Les termes saisis sont recherchés au sein : 
- du titre de la fiche de métadonnées
- du nom du fichier
- de son résumé
- de ses mots-clés
- de ses thèmes INSPIRE

Pour en savoir plus sur le fonctionnement du moteur de recherche Isogeo, [consulter l'aide en ligne](http://help.isogeo.com/fr/features/inventory/search.html).

### Utiliser les filtres contextuels

#### Filtre par mot-clé

Pour filtrer par mots-clés, cocher un ou plusieurs mots-clés dans la liste déroulante dédiée.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_options_keywords_fr.png "Filtre par mot-clé")

#### Filtre géographique

Pour filtrer les résultats sur une emprise géographique, choisir une modalité dans la liste déroulante dédiée. 
On y trouve les possibilités de filtrer sur : 

- L'emprise actuelle de la carte
- L'enveloppe convexe des couches actuellement affichées

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_options_geographic_fr.png "Filtre à partir de la carte ou d\'une couche active")

Par défaut, le filtre géographique remonte toute les données qui intersectent l'emprise considérée. 

Pour changer ce comportement, aller dans l'onglet "Paramètres", choisir un opérateur différent, puis relancer la recherche.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/settings_geographic_fr.png "Paramétrer l\'opérateur géométrique pour la recherche géographique")

#### Filtres 

Tous les autres filtres sémantiques fonctionnent de la même manière (sélection d'une modalité dans une liste déroulante). La seule exception est le filtre sur les actions disponibles pour lequel les options souhaitées doivent être cochées.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/search_options_actions_fr.png "Filtre sur les actions associées")

Tous les filtres sont inter-dépendants (contextuels). Ainsi l'application d'un filtre fait évoluer les modalités disponibles dans toutes les listes déroulantes.
