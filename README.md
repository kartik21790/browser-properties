# browser-properties
A PHP based file to find browser properties. It uses browscap.ini if set in php config, or else uses HTTP_USER_AGENT with custom regex to find browser propeties.

Provides below browser details
  - Browser Name
  - Browser Version
  - Platform i.e. OS
  - Device Type (mobile / desktop)
  - Source i.e. how properties were found, using 'browscap.ini' or 'HTTP_USER_AGENT'

# How to run

Extract/paste browser.php in any folder inside your document root.

Include it in your PHP file (example : include_once 'browser.php'; )

Refer below sample function calls and output format
--------------------
 1. array format
--------------------

$browser_info=getBrowserProperties();

 OR

$browser_info=getBrowserProperties('array');

Output:

    array(
    'browser name' => string 'Chrome' 
    'browser version' => string '51.0'
    'platform' => string 'Win10' 
    'device_type' => string 'Desktop'
    'src' => string 'browscap.ini/get_browser() PHP built-in function'
    )

--------------------
 2. html format (returns a ul with id browlistprop)
--------------------

  $browser_info=getBrowserProperties('html');
  
  Output:
  
	<ul id='browlistprop'>
      	<li>Browser Name : <b>Chrome</b></li>
          <li>Browser Version : <b>51.0</b></li>
          <li>Platform : <b>Win10</b></li>
          <li>Device_type : <b>Desktop</b></li>
  		<li>Src : <b>browscap.ini/get_browser() PHP Built-in Function</b></li>
	</ul>

#Note:
If browscap.ini is set in PHP config, value of "src" will be "browscap.ini/get_browser() PHP Built-in Function"
 
else, value of "src" will be "Regex with HTTP_USER_AGENT string"



# References
http://php.net/manual/en/function.get-browser.php#101125 for custom regex logic using HTTP_USER_AGENT string.
http://detectmobilebrowsers.com/ for detecting mobile / desktop browser using HTTP_USER_AGENT string.
