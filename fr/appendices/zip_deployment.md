---
description: Comment déployer facilement le plugin QGIS Isogeo sur plusieurs postes
---
# Déployer le plugin via un ZIP {#zip_install}

## Contexte

Une grande partie des paramétrages liés à l'utilisation du plugin Isogeo est enregistrée dans le répertoire d'installation du plugin (`C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` dans la plupart des cas). C'est notamment le cas :

* du fichier `client_secrets.json` utilisé pour l'[authentification](/usage/authentication.md#auth_file) (dans le sous-dossier `_auth`)
* des [recherches rapides](/usage/advanced/quicksearch.md) et de la [recherche par défaut](/usage/advanced/defaultsearch.md) qui sont écrites dans un fichier `quicksearches.json` (dans le sous-dossier `_user`)
* des [connexions aux bases de données configurées dans le fichier `db_connections.json`](/usage/display.md#add_tables_from_fileconnection) (dans le sous-dossier `_user`)

D'autre part, le gestionnaire des extensions de QGIS permet d'installer un plugin à partir d'un fichier `.zip`. Il est donc possible, dans le cas d'une organisation où les utilisateurs finaux du plugin Isogeo sont nombreux, de leur éviter d'avoir à effectuer eux-mêmes certains paramétrages communs à tous les utilisateurs.

>**Prenons l'exemple suivant:**
>
>Un utilisateur X est responsable de la diffusion du plugin QGIS Isogeo auprès d'une dizaine d'utilisateurs appartenant à son organisation :
>
>* le fichier d'authentification `client_secrets.json` est probablement commun à toute l'organisation
>* les données auxquelles les utilisateurs finaux pourront accéder via le plugin Isogeo sont stockées dans une même base de données à laquelle tous les utilisateurs ont accès
>* une partie de ces données est succeptible d'être utile à tous les utilisateurs
>
>Dans ce cas, l'utilisateur X peut :
>
>* authentifier le plugin avec le `client_secrets.json` commun à toute son organisation
>* configurer dans le fichier `db_connections.json` la connexion à la base de données de l'organisme
>* sauvegarder des recherches rapides englobant les métadonnées relatives à des données utiles à tous les utilisateurs
>
>Une fois ce paramétrage effectué par l'utilisateur X, il peut générer un `.zip` à partir du répertoire d'installation du plugin sur son poste et le diffuser auprès de la dizaine d'utilisateurs finaux qui n'auront pas à s'authentifier, à configurer la connexion à la base de données ou à sauvegarder certaines recherches rapides.

## Marche à suivre

1. [Installer le plugin et s'authentifier](/usage/authentication.md) en indiquant l'emplacement du fichier `client_secrets.json` fourni par l'équipe Isogeo. Le fichier est copié dans le répertoire du plugin QGIS sur l'ordinateur utilisé (dans `C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine\_auth` pour Windows ou `/home/%userprofile%/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine/_auth` pour Ubuntu).

    ![Emplacement du fichier `client_secrets.json` après l'authentification](/assets/_auth_folder_fr.png)

2. Sur le même poste, paramétrer le plugin :
   1. en sauvegardant des [recherches rapides](/usage/advanced/quicksearch.md)
   2. en établissant une [recherche par défaut](/usage/advanced/defaultsearch.md)
   3. en configurant des [connections à des bases de données dans le fichier `_user/db_connections.json`](/usage/display.md#add_tables_from_fileconnection)

3. Toujours sur le même poste, créer un fichier ZIP à partir du répertoire du plugin Isogeo  (`C:\Users\%userprofile%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` pour Windows ou `/home/%userprofile%/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine` pour Ubuntu).

    ![Création d'un fichier ZIP à partir du dossier du plugin après l'authentification](/assets/create_zip_fr.png)

    Ce fichier ZIP contient les fichiers `_auth/client_secrets.json`, `_user/quicksearches.json` et `_user/db_connections.json` résultant des deux premières étapes.

4. Diffuser le fichier ZIP ainsi créé auprès des autres utilisateurs qui pourront installer le plugin QGIS Isogeo directement à partir du fichier `isogeo_search_engine.zip` (Menu "Installer/Gérer les extensions" > onglet "Installer depuis un ZIP").

    ![1- Ouvrir le gestionnaire d'extension > onglet "Installer depuis un ZIP"](/assets/install_from_zip1_fr.png)

    ![2- Indiquer l'emplacement du fichier ZIP créé lors de l'étape précédente](/assets/install_from_zip2_fr.png)

    Pour les utilisateurs qui installeront le plugin ainsi, l'authentification sera automatique (sans passer par le formulaire d'authentification) car le fichier `client_secrets.json` sera déjà présent dans le dossier `_auth` du plugin Isogeo.
