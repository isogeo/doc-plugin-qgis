# Authentification

## Indiquer l'emplacement du fichier d'authentification {#auth_file}

Au premier lancement du plugin (ou au clic sur [le bouton de changement d'identifiants](/usage/configuration.md#authentication)), le formulaire d'authentification s'ouvre.

Utiliser le bouton `...` pour charger le fichier d'authentification (`client_secrets.json`) que vous devez avoir reçu d'Isogeo ou de votre administrateur.

!["Charger le fichier client_secrets&#46;json transmis par mail"](/assets/ui_auth_prompt_upload_credentials_file_fr.png)

Et voilà, bonne utilisation !

---

## Les erreurs SSL {#ssl_errors}

Au lancement du plugin (ou après l'[authentification](fr/usage/authentication.md) dans le cas d'une première utilisation), il est possible que le logiciel signal une erreur de certificat SSL par l'intermédiaire de la fenêtre suivante :

!["Erreur de certificat SSL signalée lors de l'authentification"](/assets/qgis_dialog_ssl_errors_id_fr.png)

!!! Note Cette boîte de dialogue indique la ou les erreurs SSL survenues lors de l'accés à une URL. Sur l'image ci-dessus il s'agit de l'URL d'authentification à l'API Isogeo (api.isogeo.com/oauth/token), cette erreur survient si le certificat SSL n'a pas encore été renouvellé par l'équipe Isogeo.

Différentes erreurs SSL sont susceptibles de survenir dans le cadre de l'utilisation du plugin QGIS Isogeo (en fonction de la configuration du proxy notamment). Elles concerneront toujours les mêmes URLs : la ou les erreurs seront signalées pour api.isogeo.com/oauth/token dans un premier temps puis pour api.isogeo.com/shares.
La boîte de dialogue de QGIS permet d'ignorer ces erreurs et ainsi de poursuivre l'utilisation du plugin :

* Les erreurs SSL peuvent être ignorées ponctuellement en cliquant sur `Ignorer`, auquel cas la ou les erreurs seront signalées au début de chaque session d'utilisation du plugin et l'utilisateur devra les ignorer pour poursuivre l'utilisation.
* Il est aussi possible de cocher la case `Sauvegarder le serveur SSL exception` avant de cliquer sur `Enregistrer & Ignorer`. Ainsi, le logiciel retient que cette erreur peut être ignorée et ne la signalera plus lors des sessions d'utilisation à venir (les exceptions SSL enregistrées dans QGIS peuvent être gérées dans Préférences > Options... > Authentification > `Gestion des Certificats` > onglet Serveurs)

!!! Note Pas d'inquiétude, les URLs de l'API Isogeo sont fiables et y accéder via le plugin QGIS n'est pas plus dangereux que se rendre sur app.isogeo.com via un navigateur.

!!! **Cas particulier :**

  !["Erreur de certificat SSL due à l'outrepassement SSL"](/assets/qgis_dialog_ssloffloading_error_fr.png)

  Dans le cas de l'image ci-dessus, l'URL d'authentification à l'API Isogeo (api.isogeo.com/oauth/token) est concernée par l'erreur suivante : "Impossible d'identifier l'origine du certificat". Cette erreur peut être due à une configuration particulière du proxy qui nécessite d'ajouter les URLs suivantes aux exceptions de l'outrepassement SSL (*SSL offloading*) du proxy :

  * id.api.isogeo.com
  * v1.api.isogeo.com
  * api.isogeo.com
  * open.isogeo.com
  * app.isogeo.com
