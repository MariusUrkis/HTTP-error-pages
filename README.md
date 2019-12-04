# Error page package for Apache and co

After cloning to the appropriate folder do the following:

1. Setup contact email: 
```Shell
sed -i 's/_EMAIL_/some@real.email/g' HTTPcode*.html
```
1. Copy logo image and tune style.css accordingly if needed
```Shell
curl -k -o logo.png https://some.location/logo.png

1. Add Apache configuration. You can edit conf-available/localized-error-pages.conf file. For other web servers check relevant configuration.

```ApacheConf
<Location /errorpages/>
        SetHandler none
        Options None
        AllowOverride None
        Order allow,deny
        Allow from all
        Satisfy Any
</Location>
Alias /errorpages/ "/var/www/HTTP-error-pages/"

ErrorDocument 400 /errorpages/HTTPcode400.html
ErrorDocument 401 /errorpages/HTTPcode401.html
ErrorDocument 403 /errorpages/HTTPcode403.html
ErrorDocument 404 /errorpages/HTTPcode404.html
ErrorDocument 500 /errorpages/HTTPcode500.html
ErrorDocument 501 /errorpages/HTTPcode501.html
ErrorDocument 502 /errorpages/HTTPcode502.html
ErrorDocument 503 /errorpages/HTTPcode503.html
```
1. Reload apache configuration
```Shell
service apache2 reload