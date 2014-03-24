CascadingResponsiveImages
=========================
<b>Introduction</b><br />
Cookie-based responsive image solution along with the configurable width settings. Requires no JavaScript. This method provides a solution to bring responsive image into JavaScript disabled websites. Depends on CSS and cookie to set/get width settings for the server to determine the optimal width for images.

This responsive image solution DO NOT require altering SRC attribute in \<img\> tag. The idea is to make the server redirect original image sources to their optimally resized image automatially. 

Upload original image in image folder and create 3 new images in responsiveImage that are rescaled to small, medium, and large.  Small images are for smartphones, medium images are for decent resolution tablets or desktop, and large images are for very large resolution (1600x1024, for example.) 

If a smartphone is loading dog.jpg, smartphone will load it as dog_s.jpg (smaller version of dog.jpg, to reduce bandwidth cost). If a retina MAC loads dog.jpg, it'll load dog_l.jpg (bigger version of dog.jpg, bigger resolution for better quality)

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


