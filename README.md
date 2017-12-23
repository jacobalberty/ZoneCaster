# ZoneCaster
This is meant to make casting to your chromecast a little easier. It works with both phone and tv and uses the media receiver
instead of just casting your web browser tab. This means you can close the tab and the stream will continue to be visible on the chromecast.

## Install
Installation is pretty simple, just copy the files to your webserver.

### Cross domain installs
If ZoneMinder isn't installed on the same webserver then you will need to edit ZoneCaster.js and change
zmServer to the address of your ZoneMinder install.
In addition you will need to add an Access-Control-Allow-Origin header. For my apache setup I use something like:

```
        <IfModule mod_headers.c>
            SetEnvIf Origin ^(https?://(?:.+\.)?mydomain\.com(?::\d{1,5})?)$   CORS_ALLOW_ORIGIN=$1
            Header append Access-Control-Allow-Origin  %{CORS_ALLOW_ORIGIN}e   env=CORS_ALLOW_ORIGIN
            Header merge  Vary "Origin"
        </IfModule>
```
to enable cross requests accross all of my subdomains.
