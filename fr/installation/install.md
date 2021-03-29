---
description: Installer le plugin Isogeo pour QGIS
---

# Installation

## Version stable {#standard}

Installation classique pour les utilisateurs standards, via le canal stable du gestionnaire d'extensions intégré à QGIS.

### Vérifier les prérequis {#requirements}

Dans QGIS, v&eacute;rifier les paramètres réseau \(proxy...\) via le menu _Pr&eacute;f&eacute;rences_ &gt; _Options..._ ;

!["V&eacute;rifier les paramètres de connexion de QGIS"](/assets/qgis_install_network_fr.png)

### Installer l'extension {#install}

Ouvrir le gestionnaire d'extensions, rechercher Isogeo et cliquer sur "Installer l'extension" :

!["Installer le plugin Isogeo depuis le gestionnaire d&apos;extensions de QGIS"](/assets/qgis_install_extension_fr.png)

---

### Versions antérieures à la 1.6.1 {#authentication_old}

Au premier lancement du plugin, entrer les identifiants reçus par mail, puis cliquer sur le bouton "Vérifier" :

* Si vos identifiants ne sont pas reconnus, un message d'erreur s'affiche et les fonctionnalités du plugin sont bloquées. Le bouton "Enregistrer" reste inactif.
* Si vos identifiants sont reconnus, le bouton "Enregistrer" s'active. Cliquer dessus pour accéder au plugin.

!["Bo&icirc;te de dialogue pour authentifier le plugin avec les cl&eacute;s API"](/assets/ui_auth_prompt_fr.png)

## Version bêta {#install_beta}

A des fins de recette ou ponctuellement pour présenter la prochaine version, il est possible d'installer la version bêta du plugin via le canal expérimental du gestionnaire d'extensions de QGIS.

1. Dans QGIS, ouvrir le Gestionnaire d'extensions : menu *Extension* > *Installer/Gérer les extensions...* ;

2. Dans *Paramètres*, activer les extensions expérimentales :

    !["Activer les extensions exp&eacute;rimentales dans les param&egrave;tres du gestionnaire d&apos;extensions"](/assets/qgis_install_experimental_settings_fr.png)

3. Il est aussi recommandé d'activer les mises à jour à chaque démarrage ou au moins hebdomadaires.

4. Cliquer sur "Recharger tous les dépôts" ;

5. Installer ou réinstaller l'extension via le gestionnaire de plugins de QGIS.

## Versions de développement {#install_dev}

Pour les développeurs ou à des fins de test, il est possible d'utiliser les versions au plus proche du développement. Les méthodes décrites ici sont destinées aux développeurs ou utilisateurs expérimentés.

### Installer la dernière version packagée

1. Télécharger la [dernière version du plugin](https://github.com/isogeo/isogeo-plugin-qgis/releases) ;
2. Décompresser dans `C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins` pour Windows ou `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins` pour Ubuntu.

### Installer une version en développement

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