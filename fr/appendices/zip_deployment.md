---
description: Comment déployer facilement le plugin QGIS Isogeo sur plusieurs postes
---
# Déployer le plugin via un ZIP {#zip_install}

## Contexte

Lors d'une première utilisation du plugin QGIS Isogeo, l'emplacement du fichier `client_secrets.json` doit être indiqué pour procéder à l'authentification. Le fichier est ensuite déplacé dans le dossier du plugin (`C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine\_auth` pour Windows ou `/home/%userprofile%/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine/_auth` pour Ubuntu). Ce comportement peut compliquer le déploiement du plugin QGIS Isogeo auprès des utilisateurs.

## Marche à suivre

1. [Installer le plugin Isogeo et s'authentifier](/usage/authentication.md) en indiquant l'emplacement du fichier `client_secrets.json` fourni par l'équipe Isogeo. Le fichier est déplacé dans le dossier du plugin QGIS sur l'ordinateur utilisé (dans `C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine\_auth` pour Windows ou `/home/%userprofile%/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine/_auth` pour Ubuntu).

    ![Emplacement du fichier `client_secrets.json` après l'authentification](/assets/_auth_folder_fr.png)

2. Créer un fichier ZIP à partir du dossier du plugin QGIS sur l'ordinateur utilisé lors de la première étape (`C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` pour Windows ou `/home/%userprofile%/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine` pour Ubuntu).

    ![Création d'un fichier ZIP à partir du dossier du plugin après l'authentification](/assets/create_zip_fr.png)

    Ce fichier ZIP contient le fichier `client_secrets.json` qui a été déplacé lors de la première étape.

3. Diffuser le fichier ZIP ainsi créé auprès des autres utilisateurs qui pourront installer le plugin QGIS Isogeo directement à partir du fichier `isogeo_search_engine.zip`.

    ![1- Ouvrir le gestionnaire d'extension > onglet "Installer depuis un ZIP"](/assets/install_from_zip1_fr.png)

    ![2- Indiquer l'emplacement du fichier ZIP créé lors de l'étape précédente](/assets/install_from_zip2_fr.png)

    Pour les utilisateurs qui installeront le plugin ainsi, l'authentification sera automatique (sans passer par le formulaire d'authentification) car le fichier `client_secrets.json` sera déjà présent dans le dossier du plugin.
