# Requirements

## Technical environment {#technical}

### Version de QGIS

QGIS 3.x LTR version (+ 3 months) - check [the roadmap and the release schedule](https://www.qgis.org/fr/site/getinvolved/development/roadmap.html#release-schedule)

### Proxy and firewall

It is essential that the computer on which the plugin is used has an authorized and configured connection (proxy, firewall...) to [https://v1.api.isogeo.com/\*](https://v1.api.isogeo.com/) and [https://id.api.isogeo.com/\*](https://v1.api.isogeo.com/).

If a proxy is configured in Windows, it must also be configured [in QGIS](https://docs.qgis.org/3.4/fr/docs/user_manual/introduction/qgis_configuration.html#network-settings).

In the case of particular proxy configurations, it will be necessary to add the following URLs to the proxy's SSL offloading exceptions:

  * id.api.isogeo.com
  * v1.api.isogeo.com
  * api.isogeo.com
  * open.isogeo.com
  * app.isogeo.com

___

## Isogeo requirements

### To use your own data

* at least an Isogeo workgroup,
* at least a catalog with at least one metadata shared to the plugin,
* Isogeo credentials to authenticate the API requests.

### Try it

If you don't have an Isogeo account yet but you want to try the Isogeo plugin for QGIS, please [complete this form](https://pipedrivewebforms.com/form/73f6215ad660efcc946e1e6d9ff0f62a52944).
