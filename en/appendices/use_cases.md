# Use cases

## Deploy Isogeo plugin with a ZIP file {#zip_install}

### Context

When using the QGIS Isogeo plugin for the first time, the location of the `client_secrets.json` file must be specified to perform authentication. The file is then moved to the plugin folder (`C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` for Windows or `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine` for Ubuntu). This behavior can make it difficult to deploy the QGIS Isogeo plugin.

### Marche à suivre

1. [Install Isogeo plugin and authenticate](/installation/standard.md) by indicating the location of the `client_secrets.json` file provided by Isogeo. The file is moved to the QGIS plugin folder (in `C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine\_auth` for Windows or `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine/_auth` for Ubuntu).

    ![`client_secrets.json` file location after the authentication](/assets/_auth_folder_en.png)

2. Create a ZIP file from the QGIS plugin folder on the computer used in the first step (`C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins\isogeo_search_engine` for Windows or `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins/isogeo_search_engine` for Ubuntu).

    ![Creating a ZIP file from the plugin folder after authentication](/assets/create_zip_en.png)

    This ZIP file contains the file `client_secrets.json` that was moved during the first step.

3. Distribute the created ZIP file to other users who will be able to install the QGIS Isogeo plugin directly from the file `isogeo_search_engine.zip`.

    ![1- Open the plugin manager > 'Install from ZIP'](/assets/install_from_zip1_en.png)

    ![2- Indicate the location of the ZIP file created in the previous step](/assets/install_from_zip2_en.png)

    For users who install the plugin in this way, authentication will be automatic (without going through the authentication form) because the file `client_secrets.json` will already be present in the plugin folder.
