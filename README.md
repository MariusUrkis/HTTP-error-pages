# Error page package for Apache and co

After cloning to the appropriate folder do the following:

1. Setup contact email
```
sed -i 's/_EMAIL_/some@real.email/' HTTPcode*.html
```
1. Copy logo image and tune style.css accordingly
1. Add Apache configuration to the virtual host section. For other web servers check relevant configuration.

```
ErrorDocument 400 /errorpages/HTTPcode400.html
ErrorDocument 401 /errorpages/HTTPcode401.html
ErrorDocument 403 /errorpages/HTTPcode403.html
ErrorDocument 404 /errorpages/HTTPcode404.html
ErrorDocument 500 /errorpages/HTTPcode500.html
ErrorDocument 501 /errorpages/HTTPcode501.html
ErrorDocument 502 /errorpages/HTTPcode502.html
ErrorDocument 503 /errorpages/HTTPcode503.html
```
