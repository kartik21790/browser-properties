# browser-properties
A PHP based file to find browser properties. It uses browscap.ini if set in php config, or else uses HTTP_USER_AGENT with custom regex to find browser propeties.

# How to run
Just extract/paste browser.php in any folder inside your document root, and open it in browser.

# References
http://php.net/manual/en/function.get-browser.php#101125 for custom regex logic using HTTP_USER_AGENT string.
http://detectmobilebrowsers.com/ for detecting mobile / desktop browser using HTTP_USER_AGENT string.
