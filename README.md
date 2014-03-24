CascadingResponsiveImages
=========================
<b>Introduction</b><br />
Cookie-based responsive image solution along with the configurable width settings. Requires no JavaScript. This method provides a solution to bring responsive image into JavaScript disabled websites. Depends on CSS and cookie to set/get width settings for the server to determine the optimal width for images.

<b>Installation requirements</b><br />
Need permission to modify .htaccess

<b>Usage requirements (client-side)</b><br />
CSS and cookie must be enabled in the browser settings.
Include importDetect.css stylesheet into the document.

<b>Configuration</b><br />
On .htaccess, change '\<your domain\>' to your ip address or your domain (192.100.100.100, example.com.  Do not include http://)

.htaccess creates a cookie based on  URL parameters given by CSS.
.htaccess will redirect original image to their optimal resized image based on cookie named MW. (if cookie MW=large, dog.jpg will get redirected to dog_l.jpg)

The cookie 'mw' will contain a value such as 'large','medium','small', etc. (You can create more if desired)


