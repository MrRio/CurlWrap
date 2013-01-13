cURL Class
==========

This is a wrapper class I wrote AGES ago to make using cURL a little nicer. 
Could use some love as its written for PHP4. As you can see by the example, I was using Ubuntu Edgy 6.10 at the time.

```php
$curl = new Curl();
$curl->url = 'http://example.com/';

// Set options like this
$curl->post = true; 

// Sent key/val pairs as an array, will automatically URL encode this
$curl->postFieldsArray = array(
	'field1' => 'value1', 
	'field2' => 'value2'
);

$curl->followLocation = true; 
$curl->userAgent = 'Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.8.1.1) Gecko/20060601 Firefox/2.0.0.1 (Ubuntu-edgy)'; 

// execute() returns the output instead of writing it straight to the page like normal cURL
$output = $curl->execute(); 

// Matches the first set of these, and returns whats in between 
$curl->grab('<head>', '</head>');	
```