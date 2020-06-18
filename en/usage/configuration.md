# Configuration and settings

## Change API credentials {#authentication}

In the `Settings` tab, it's possible to change API keys:

![](/assets/settings_switch_api_en.png "Change API authentication")

---

## Share catalogs to the plugin {#shares}

Create a share to the application *QGIS Plugin* in the administration console on [APP](https://app.isogeo.com/admin/shares);

![](/assets/app_share_toPlugin_en.png "A share to publish metadata into the plugin from Isogeo administration console")

---

## Display shares which are feeding the plugin {#app_properties}

In the `Settings` tabs, informations about shares feeding the application are displayed:

![](/assets/settings_shares_details_en.png "Informations about application in the Settings tab")

* name of the application declared to the Isogeo platform, corresponding to the plugin in use,
* count of shares feeding the plugin in use. Then, each share is described:
  * the share name - a clic opens the administration console on Isogeo,
  * the share last update,
  * the Isogeo workgroup owning the share and its email contact

## Add metadata Isogeo Portal's URL to added layers'properties {#metadata_portal_url}

> This section only concerns users of the QGIS plugin who also have access to the [Isogeo Portal].(https://www.isogeo.com/nos-produits/Portail)

This functionality involves two prerequisites:

* some catalogs shared to the QGIS plugin are also shared to the Isogeo Portal
* some metadata sheets shared meet [the requirements for adding layers to the canvas](/usage/display.md#add_criteria)

If these 2 prerequisites are satisfied, the URL of the metadata sheet of the Isogeo Portal corresponding to the layer added to the canvas will appear in the "Properties" of this layer (in the "Url of the data" field of the "Description" section of the "QGIS Server" tab).:

![Propriétés de la couche, onglet "QGIS Server"](/assets/layer_properties_portal_data_url_fr.png)

In order to obtain this result, it is necessary to check the corresponding box in the "Parameters" tab of the plugin and to indicate in the text field the base of the Portal's URL as below:

![Paramètres du Portail isogeo](/assets/settings_isogeo_portal_en.png)