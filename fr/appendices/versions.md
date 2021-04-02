---
description: Changelog des versions du plugin Isogeo pour QGIS
---

# Notes de versions

<!-- timeline -->
## 3.2.0 {#version320}

<br>Publiée le 2 avril 2021 :

> ### [Consulter la Release sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/3.2.0)

* meilleure gestion des connexions aux bases de données PostgeSQL:
  * possibilité de choisir la connexion utilisée par le plugin pour accéder aux tables de chaque base de données : [#320](https://github.com/isogeo/isogeo-plugin-qgis/issues/320):
    * [au moment d'ajouter une couche PostGIS](/usage/configuration.md#pgdb_connections_default)
    * [de manière durable via une interface dédiée](/usage/configuration.md#pgdb_connections_config)
  * prise en compte des [connexions via des services](/usage/display.md#add_postgis) configurés dans un fichier `pg_service.conf` : [#321](https://github.com/isogeo/isogeo-plugin-qgis/issues/321)
* corrections de bugs :
  * majeurs : [#355](https://github.com/isogeo/isogeo-plugin-qgis/issues/355)
  * mineurs : [#110](https://github.com/isogeo/isogeo-plugin-qgis/issues/110), [#279](https://github.com/isogeo/isogeo-plugin-qgis/issues/279), [#353](https://github.com/isogeo/isogeo-plugin-qgis/issues/353)
* améliorations mineures : [#359](https://github.com/isogeo/isogeo-plugin-qgis/issues/359), [#274](https://github.com/isogeo/isogeo-plugin-qgis/issues/274)

<!-- /timeline -->

<!-- timeline -->
## 3.1.1 {#version311}

<br>Publiée le 4 février 2021 :

> ### [Consulter la Release sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/3.1.1)

* refonte et amélioration des performances :
  * de la fonctionnalité d'ajout de couche à la carte : [#318](https://github.com/isogeo/isogeo-plugin-qgis/issues/318)
  * du remplissage du tableau des résultats : [#316](https://github.com/isogeo/isogeo-plugin-qgis/issues/316), [#330](https://github.com/isogeo/isogeo-plugin-qgis/issues/330)
* meilleure gestion des spécificités des services géographiques (OGC et ESRI): [#341](https://github.com/isogeo/isogeo-plugin-qgis/issues/341), [#348](https://github.com/isogeo/isogeo-plugin-qgis/issues/348), [#349](https://github.com/isogeo/isogeo-plugin-qgis/issues/349), [#350](https://github.com/isogeo/isogeo-plugin-qgis/issues/350), [#351](https://github.com/isogeo/isogeo-plugin-qgis/issues/351)
* corrections de bugs :
  * majeurs : [#336](https://github.com/isogeo/isogeo-plugin-qgis/issues/336), [#337](https://github.com/isogeo/isogeo-plugin-qgis/issues/337)
  * mineurs : [#339](https://github.com/isogeo/isogeo-plugin-qgis/issues/339), [#345](https://github.com/isogeo/isogeo-plugin-qgis/issues/345)
* améliorations mineures : [#333](https://github.com/isogeo/isogeo-plugin-qgis/issues/333), [#340](https://github.com/isogeo/isogeo-plugin-qgis/issues/340), [#343](https://github.com/isogeo/isogeo-plugin-qgis/issues/343)

<!-- /timeline -->

<!-- timeline -->

## 3.1.0 {#version310}

<br> Publiée le 17 décembre 2020 :

> ### [Consulter la Release sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/3.1.0)

* informer l'utilisteur à propos des limitations auxquelles les données qu'il ajoute au caneva sont sujettes : [#164](https://github.com/isogeo/isogeo-plugin-qgis/issues/164)
* permettre l'écriture automatique de l'URL de la fiche de métadonnées du portail Isogeo dans les propriétés des couches ajoutées au caneva : [#312](https://github.com/isogeo/isogeo-plugin-qgis/issues/312)
* ajout de ressources dans la fenêtre d'authentification facilitant l'essai du plugin pour les utilisateurs ne disposant pas encore de compte Isogeo : [#325](https://github.com/isogeo/isogeo-plugin-qgis/issues/325)
* corrections de bug : [#332](https://github.com/isogeo/isogeo-plugin-qgis/issues/332), [#331](https://github.com/isogeo/isogeo-plugin-qgis/issues/331), [#309](https://github.com/isogeo/isogeo-plugin-qgis/issues/309), [#280](https://github.com/isogeo/isogeo-plugin-qgis/issues/280)
* améliorations mineures : [#298](https://github.com/isogeo/isogeo-plugin-qgis/issues/298), [#327](https://github.com/isogeo/isogeo-plugin-qgis/issues/327)

<!-- /timeline -->

<!-- timeline -->

## 3.0.2 {#version302}

<br> Publiée le 28 janvier 2020 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/13?closed=1)

* meilleur gestion des erreurs due aux certificats SSL [#299](https://github.com/isogeo/isogeo-plugin-qgis/pull/299)

<!-- /timeline -->

<!-- timeline -->

## 3.0.1 {#version301}

<br> Publiée le 25 octobre 2019 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/11?closed=1)

* correction d'un problème bloquant durant l'authentification [#296](https://github.com/isogeo/isogeo-plugin-qgis/issues/296)

<!-- /timeline -->

<!-- timeline -->

## 3.0.0 {#version300}

<br> Publiée le 23 octobre 2019 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/3?closed=1)

* [portage du plugin vers QGIS LTR 3.4.x](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/v2.0.0-alpha1)
* refactoring du code source :
  * [beta 1](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/2.0.0-beta1)
  * [beta 2](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/2.0.0-beta2)
  * [beta 3](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/2.0.0-beta3)
  * [beta 4](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/2.0.0-beta4)
  * [première version stable pour QGIS 3](https://github.com/isogeo/isogeo-plugin-qgis/releases/tag/3.0.0)

<!-- /timeline -->

<!-- timeline -->

## 1.6.3 {#version163}

<br> Publiée le 1er février 2019 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/8?closed=1)

* correction d'un problème bloquant l'installation [#165](https://github.com/isogeo/isogeo-plugin-qgis/issues/165)
* correction d'un problème bloquant l'ajout de données raster [#166](https://github.com/isogeo/isogeo-plugin-qgis/issues/166)

<!-- /timeline -->

<!-- timeline -->

## 1.6.2 {#version162}

<br> Publiée le 30 novembre 2018 :

* amélioration du système de cache [#135](https://github.com/isogeo/isogeo-plugin-qgis/issues/135)

<!-- /timeline -->

<!-- timeline -->

## 1.6.1 {#version161}

<br> Publiée le 1er août 2018 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/7?closed=1)

* amélioration du rapport d'anomalie [#139](https://github.com/isogeo/isogeo-plugin-qgis/issues/139#issuecomment-405258056)
* l'authentification à l'API Isogeo est désormais capable de gérer d'autres isntances que celle de la plateforme Isogeo. Requis pour une installation [_on-premises_](https://fr.wikipedia.org/wiki/Auto-h%C3%A9bergement_(Internet)). [#149](https://github.com/isogeo/isogeo-plugin-qgis/issues/149)
* corrections d'anomalies mineures :
  * depuis la version précédente, certaines icônes ne s'affichaient pas dans la fiche de métadonnées [#147](https://github.com/isogeo/isogeo-plugin-qgis/issues/147 et [#148](https://github.com/isogeo/isogeo-plugin-qgis/issues/148))
  * une erreur pouvait intervenir dans certains cas de chargement de données fichiers [#129](https://github.com/isogeo/isogeo-plugin-qgis/issues/129)
  * des fenêtres d'information à l'utilisateur ne fonctionnaient pas
  * le fond de carte d'une métadonnée détaillée ne s'affichait [plus #150](https://github.com/isogeo/isogeo-plugin-qgis/issues/150)

<!-- /timeline -->

<!-- timeline -->

## 1.6 {#version16}

<br> Publiée le 30 avril 2018 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/6?closed=1)

* ajout des filtres contacts et licences
* ajout du filtre sur toutes les données (vecteur ET raster) dans le type
* ajout de la possibilité d'ajouter les services Esri (Feature et Map) documentés sur Isogeo
* gestion de l'ordre des formats à ajouter
* finalisation de la fenêtre d'authentification
* remaniement de l'interface de recherche
* corrections d'anomalies mineures

<!-- /timeline -->

<!-- timeline -->

## 1.5 {#version15}

<br> Publiée le 30 mai 2017 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/5?closed=1)

* refonte de la fiche de métadonnées : informations complètes, présentation en onglets, design.
* gestion des nouvelles métadonnées de service Isogeo : appel du _GetCapabilities_ pour les informations complémentaires, optimisation de la construction d'URL d'ajout à QGIS, gestion des espaces de nommage
* gestion automatique des vues PostgreSQL
* remplissage des informations sur la couche dans QGIS à partir des métadonnées Isogeo
* réduction de la liste de résultats à 10 éléments (au lieu de 15)
* corrections d'anomalies : recherche par SRS, problèmes dans l'ajout de services, informations sur les partages dans l'onglet des paramètres.

<!-- /timeline -->
<!-- timeline -->

## 1.2 {#version12}

<br> Publiée le 28 décembre 2016 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/2?closed=1)

* ajout d'une fenêtre "A propos" avec les crédits
* ajout de messages d'informations temporaires dans QGIS
* ajout de la valeur "Aucun" aux filtres
* refonte de l'onglet des paramètres
* traduction de tous les intitulés dans la fiche de métadonnées détaillée
* support de QGIS 2.16
* documentation utilisateur
* corrections diverses : ajout WMS, plantages, encodage, barres de progression...

<!-- /timeline -->
<!-- timeline -->

## 1.0 {#version10}

<br> Publiée le 1er octobre 2016 :

> [Consulter la fiche de version sur Github.](https://github.com/isogeo/isogeo-plugin-qgis/milestone/1?closed=1)

* produit minimum atteint ;
* socle fonctionnel de base : recherche textuelle, filtres dynamiques, recherche géographique, affichage des résultats, ajout des données, fiche de métadonnées minimaliste, recherches rapides, etc.

<!-- /timeline -->
