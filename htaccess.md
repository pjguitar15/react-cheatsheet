# Use this to redirect your website back

ErrorDocument 404 /index.html
RewriteEngine On
RewriteCond %{HTTP_HOST} !^www\.
RewriteRule ^(.*)$ https://www.%{HTTP_HOST}/$1 [R=301,L]

ErrorDocument 404 /index.html
RewriteEngine On
RewriteCond %{HTTP_HOST} iltp\.org [NC]
RewriteCond %{SERVER_PORT} 80
RewriteRule ^(.*)$ https://iltp.org/$1 [R,L]

