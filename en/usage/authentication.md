# Authentication

## Specify the location of the authentication file {#auth_file}

Isogeo is a secured SaaS platform, so applications which use its data have to be authenticated (oAuth2 protocol). API credentials are a key pair, with an _id_ and a _secret_. When the plugin is launched for the first time (or otherwise when clicking on the [change API credentials button](/usage/configuration.md#authentication)), the [authentication form](/installation/standard.md#auth-form) shows up.

Click `...` button to load crdentials file (`client_secrets.json`) provided by Isogeo or your administrator.

!["Load the credentials file client_secrets&#46;json received by email"](/assets/ui_auth_prompt_upload_credentials_file_en.png)

---

## SSL certificate errors {#ssl_errors}

When the plugin is launched (or after authentication in the case of a first use), it is possible that QGIS report an SSL certificate error via the following window:

!["SSL Certificate Error Reported During Authentication"](/assets/qgis_dialog_ssl_errors_id_fr.png)

> Note This dialog window displays the SSL error(s) that occurred when accessing a URL. In the image above it is the authentication URL to the Isogeo API (api.isogeo.com/oauth/token), this error occurs if the SSL certificate has not yet been renewed by the Isogeo team.

Different SSL errors may occur when using the QGIS Isogeo plugin (depending on the proxy configuration in particular). They will always concern the same URLs: the error(s) will be reported for api.isogeo.com/oauth/token first and then for api.isogeo.com/shares.
The QGIS dialog box allows to ignore these errors and thus to continue using the plugin :

* SSL errors can be occasionally ignored by clicking 'Ignore', in which case the error(s) will be reported at the beginning of each session of plugin use and the user will have to ignore them in order to continue using the plugin.
* It is also possible to check the `Save SSL server exception` checkbox before clicking `Save & Ignore`. This way, the software remembers that this error can be ignored and will not report it in future user sessions (SSL exceptions registered in QGIS can be managed in Preferences > Options... > Authentication > `Certificate Management` > Servers tab)

> **Special case :**
>
>!["SSL Certificate Error due to SSL offloading"](/assets/qgis_dialog_ssloffloading_error_fr.png)
>
>In the case of the image above, the authentication URL to the Isogeo API (api.isogeo.com/oauth/token) is affected by the following error: "Unable to identify the origin of the certificate". This error may be due to a particular proxy configuration that requires the following URLs to be added to the SSL offloading exceptions of the proxy :
>
>* id.api.isogeo.com
>* v1.api.isogeo.com
>* api.isogeo.com
>* open.isogeo.com
>* app.isogeo.com
