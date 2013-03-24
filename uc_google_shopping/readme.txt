Google Base RSS Feed
Version: 	2.3.1
Author:		Daniel A. Baker
e-Mail:		danbaker@wkacorp.com
URL:		http://www.wkacorp.com / http://www.reputabletech.com


Compatability:
Drupal 		6.12
Ubercar 	2.x
RSS:		2.0
XML:		1.0



Based on Google Base for Ubercart 1.0.

Author:		Josh Huckabee. 
URL:		http://joshhuckabee.com/

Source File: http://www.ubercart.org/contrib/1975


------------------------------------------------------------------------------------------------------
To access, simply point Google's Base Data Feed to: http://www.yoursite.com/products/google_base.xml

Add Functionality:
You can add any functionality you like, the known variables for google are here: http://base.google.com/support/bin/answer.py?hl=en&answer=78170
------------------------------------------------------------------------------------------------------

Version Updates:
------------------------------------------------------------------------------------------------------
2.3.1:
6/21/2009, 11:07am, PDT.


Removed

    $output .= "<g:upc>000000000000</g:upc>\n";

To prevent invalid information from being passed to Google Base.
Fixed duplicate entry in readme.txt



------------------------------------------------------------------------------------------------------
2.3:
6/20/2009, 10:37am, PDT.

Added functionality for Quantity, and Item Location. Item location pulls store address from store information. Currently does not pull store state, only street, city and zip, (should be enough for google to accurately process).
Added code:

$store_zip = variable_get('uc_store_postal_code', '');
$store_addy = variable_get('uc_store_street1', '');
$store_city = variable_get('uc_store_city', '');


    $output .= "<g:location>$store_addy" . ', ' . "$store_city" . ', ' . "$store_zip</g:location>\n";
    $output .= "<g:quantity>" . $product->pkg_qty . "</g:quantity>\n";



------------------------------------------------------------------------------------------------------
2.2:
6/20/2009, 9:18am, PDT.

Added Readme.txt
Added weight tag, including unit of measurement for Google Base.
Added Code:
    $output .= "<g:weight>" . $product->weight . ' ' . $product->weight_units . "</g:weight>\n";



------------------------------------------------------------------------------------------------------
2.1:
6/19/2009, 11:50pm, PDT.

Replaced "list Price" with "Sell Price." 
Toggled global URL for item specific URL.

Previous Code:
    $output .= "<g:price>" . $product->list_price . "</g:price>\n";
    $output .= "<link>" . $GLOBALS['base_url'] . '/' . $product->path . "</link>\n";

Changed Code:
    $output .= "<g:price>" . $product->sell_price . "</g:price>\n";
    $output .= "<link>" . $GLOBALS['base_url'] . '/node/' . $product->nid . "</link>\n";
------------------------------------------------------------------------------------------------------
2.0
6/18/2009, 11:42am, EST.

Drupal 6.x Compatability re-written.
Author: NecroHill
URL:	http://www.ubercart.org/user/3173
------------------------------------------------------------------------------------------------------