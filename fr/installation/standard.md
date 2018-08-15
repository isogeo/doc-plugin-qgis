# Installation standard

Installation classique pour les utilisateurs standards, via le canal stable du gestionnaire d'extensions intégré à QGIS.

## Vérifier les prérequis {#requirements}

Dans QGIS, v&eacute;rifier les paramètres réseau \(proxy...\) via le menu _Pr&eacute;f&eacute;rences_ &gt; _Options..._ ;

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/fr/qgis_install_network_fr.png "V&eacute;rifier les paramètres de connexion de QGIS")

## Installer l'extension {#install}

Ouvrir le gestionnaire d'extensions, rechercher Isogeo et cliquer sur "Installer l'extension" :

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/fr/qgis_install_extension_fr.png "Installer le plugin Isogeo depuis le gestionnaire d&apos;extensions de QGIS")

## Connecter le plugin à Isogeo {#authentication}

Au premier lancement du plugin (ou au clic sur [le bouton de changement d'identifiants](/usage/configuration.md)), le formulaire d'authentification s'ouvre.

Utiliser le bouton `...` pour charger le fichier d'authentification (`client_secrets.json`) que vous devez avoir reçu d'Isogeo ou de votre administrateur.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/fr/ui_auth_prompt_upload_credentials_file_fr.png "Charger le fichier client_secrets&#46;json transmis par mail")

Et voilà, bonne utilisation !

---

## Versions antérieures à la 1.6.1 {#authentication_old}

Au premier lancement du plugin, entrer les identifiants reçus par mail, puis cliquer sur le bouton "Vérifier"

   * Si vos identifiants ne sont pas reconnus, un message d'erreur s'affiche et les fonctionnalités du plugin sont bloquées. Le bouton "Enregistrer" reste inactif.

   * Si vos identifiants sont reconnus, le bouton "Enregistrer" s'active. Cliquer dessus pour accéder au plugin.

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/fr/ui_auth_prompt_fr.png
   "Bo&icirc;te de dialogue pour authentifier le plugin avec les cl&eacute;s API")


