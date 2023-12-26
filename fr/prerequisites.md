# Prérequis

## Environnement technique {#technical}

### Version de QGIS

Le plugin Isogeo fonctionne sur QGIS 3.16.x à 3.28.x (consulter [le calendrier des sorties](https://www.qgis.org/fr/site/getinvolved/development/roadmap.html#release-schedule)).

### Proxy et pare-feu

Il est indispensable que l'ordinateur sur lequel le plugin est utilisé dispose d'une connexion autorisée et configurée (proxy, pare-feu...) vers [https://v1.api.isogeo.com/\*](https://v1.api.isogeo.com/) et [https://id.api.isogeo.com/\*](https://v1.api.isogeo.com/).

Si un proxy est configuré dans Windows, il doit l'être également [dans QGIS](https://docs.qgis.org/3.4/fr/docs/user_manual/introduction/qgis_configuration.html#network-settings).

Dans le cas de certaines configurations proxy particulières, il sera nécessaire d'ajouter les URLs suivantes aux exceptions de l'outrepassement SSL (*SSL offloading*) du proxy :

* id.api.isogeo.com
* v1.api.isogeo.com
* api.isogeo.com
* open.isogeo.com
* app.isogeo.com

> NB : En mode On-premises, les urls de l'API Isogeo doivent également être accessibles sur le poste client.
___


## Accès Isogeo {#Isogeo}

### Pour consulter ses propres données

* au moins un groupe de travail Isogeo ;
* au moins un catalogue contenant au moins une métadonnée, partagé au plugin QGIS ;
* des clés d'authentification auprés de l'API Isogeo ;