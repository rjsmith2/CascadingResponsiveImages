CascadingResponsiveImages
=========================
<b>Introduction</b><br />
Cookie-based responsive image solution along with the configurable width settings. Requires no JavaScript. This method provides a solution to bring responsive image into JavaScript disabled websites. Depends on CSS and cookie to set/get width settings for the server to determine the optimal width for images.

<b>Installation requirements</b><br />
Access to modify scripts serverside (.htaccess, PHP, etc)

<b>Usage requirements (client-side)</b><br />
CSS and cookie must be enabled in the browser settings.

<b>Configuration</b><br />
On .htaccess, change '\<your domain\>' to your ip address or your domain (192.100.100.100, example.com.  Do not include http://)

.htaccess creates a cookie based on GET parameter given by CSS.
.htaccess will redirect original image to their optimal resized image based on cookie. (if cookie MW=large, dog.jpg will get redirected to dog_l.jpg)

The cookie 'mw' will contain a value such as 'large','medium','small', etc. (You can create more if needed)

To create a more cookie values like 'large'. Copy and paste and replace 'large' to something else and rename '$1_l.$2'. So if you wish to make a new cookie value called retina to display 4k resolution image, then replace large to retina and change /responsiveImage/$1_l.$2 to /responsiveImage/$1_r.$2 (notice the change from _l to _r)
# 
	RewriteCond %{REQUEST_URI} transparent.gif [NC]
	RewriteCond %{QUERY_STRING} ^(.*?)mw=(large) [NC]
	RewriteRule (.*) $1 [QSA,L,R=204,CO=mw:large:<your domain>:1440:/]
	RewriteCond %{REQUEST_URI} ^(.*?)\.(jpg|png|jpeg|bmp|gif)  [NC]
	RewriteCond %{REQUEST_URI} !/responsiveImage/ [NC]
	RewriteCond %{HTTP_COOKIE} mw=(large) [NC]
	RewriteRule ^.*?image/(.*?)\.(.*?)$ http://<your domain>/responsiveImage/$1_l.$2 [R=302,L]#


