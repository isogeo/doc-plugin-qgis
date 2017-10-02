# Configuration and settings

## Authentication


### 

The [authentication form](/installation/standard.md#auth-form) show up when:

* the plugin is launched for the first time,
* the API credentials have expired.

### Change API credentials

In the `Settings` tab, it's possible to change API keys:

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/settings_switch_api_en.png "Change API authentication")

---

## Share catalogs to the plugin


Create a share to the application *QGIS Plugin* in the administration console on [APP](https://app.isogeo.com/admin/shares);

<img src="https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/app_share_toPlugin_en.png" alt="A share to publish metadata into the plugin from Isogeo administration console" height="350" align="center" />

---

## Display shares which are feeding the plugin

In the `Settings` tabs, informations about the application are displayed:

![](https://raw.githubusercontent.com/isogeo/isogeo-plugin-qgis/master/img/settings_shares_details_en.png "Informations about application in the Settings tab")

* name of the application declared to the Isogeo platform, corresponding to the plugin in use,
* count of shares feeding the plugin in use. Then, each share is described:
  * the share name - a clic opens the administration console on Isogeo,
  * the share last update,
  * the Isogeo workgroup owning the share and its email contact
