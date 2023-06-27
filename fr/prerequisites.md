# Pr&eacute;requis

## Environnement technique {#technical}

### Version de QGIS

Le plugin Isogeo fonctionne sur QGIS 3.16.x à 3.28.x (consulter [le calendrier des sorties](https://www.qgis.org/fr/site/getinvolved/development/roadmap.html#release-schedule)).

### Proxy et pare-feu

Il est indispensable que l'ordinateur sur lequel le plugin est utilisé dispose d'une connexion autoris&eacute;e et configur&eacute;e (proxy, pare-feu...) vers [https://v1.api.isogeo.com/\*](https://v1.api.isogeo.com/) et [https://id.api.isogeo.com/\*](https://v1.api.isogeo.com/).

Si un proxy est configuré dans Windows, il doit l'être également [dans QGIS](https://docs.qgis.org/3.4/fr/docs/user_manual/introduction/qgis_configuration.html#network-settings).

Dans le cas de certaines configurations proxy particulières, il sera nécessaire d'ajouter les URLs suivantes aux exceptions de l'outrepassement SSL (*SSL offloading*) du proxy :

* id.api.isogeo.com
* v1.api.isogeo.com
* api.isogeo.com
* open.isogeo.com
* app.isogeo.com

___

## Accès Isogeo {#Isogeo}

### Pour consulter ses propres donn&eacute;es

* au moins un groupe de travail Isogeo ;
* au moins un catalogue contenant au moins une m&eacute;tadonn&eacute;e, partag&eacute; au plugin QGIS ;
* des cl&eacute;s d'authentification aupr&eacute;s de l'API Isogeo ;

### Essayer le plugin {#try-it}

Vous ne disposez pas encore d'un compte Isogeo mais vous souhaitez essayer le plugin Isogeo pour QGIS ? Merci de [remplir ce formulaire](https://pipedrivewebforms.com/form/73f6215ad660efcc946e1e6d9ff0f62a52944).
