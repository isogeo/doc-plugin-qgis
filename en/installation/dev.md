# Installation for development

**Developers** should use latest versions.

## Last packaged version

1. Download the [last plugin version released](https://github.com/isogeo/isogeo-plugin-qgis/releases) ;
2. Unzip it in `C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins` on Windows or `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins` on Ubuntu ;

## Development version

* **plugin version 2.x**

    Clone the repository in  `C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins` on Windows or `/home/$USER/.local/share/QGIS/QGIS3/profiles/default/python/plugins` on Ubuntu, specifiying a foldername **without special character nor hyphen** (unlike the repository name...):

    ```bash
    cd C:\Users\%USERNAME%\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins
    git clone https://github.com/isogeo/isogeo-plugin-qgis.git isogeo_search_engine_dev
    ```

* **plugin version 1.x**

    Clone the repository in  `C:\Users\%USERNAME%\.qgis2\python\plugins` on Windows or `/home/$USER/.qgis2/python/plugins` on Ubuntu, specifiying a foldername **without special character nor hyphen** (unlike the repository name...):

    ```bash
    cd C:\Users\%USERNAME%\.qgis2\python\plugins
    git clone https://github.com/isogeo/isogeo-plugin-qgis.git isogeo_search_engine_dev --branch qgis2
    ```

It's also possible to clone the repository in any folder and add its path to the environment variable `QGIS_PLUGINPATH` (whatever the plugin version).
