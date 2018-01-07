# GeoIP-API
Revplit provides free usage of its Geo IP API through multiple response formats.  We support IPv4 and IPv6.

# Usage limits

Our system will automatically ban any IP addresses doing over 150 requests per minute. To unban your IP you'll have to sent a email to revplit.service@gmail.com

You are free to use our API for non-commercial and commercial use.

# Response formats
PHP https://revplit.com/pages/api/php-response.php

JSON https://revplit.com/pages/api/json-response.php

CSV https://revplit.com/pages/api/csv-response.php

# Code sample

<code>
<?php
  $result = "";
    if(isset($_POST['sub'])) {
      $ip = $_POST['ip'];
      if(!empty($_POST['ip'])) {
        $result = @file_get_contents("https://api.revplit.com/geo/all.php?ip=".$ip);
      } else {
           $result = "No IP filled in";
        }
       }
?>

<form method="POST">
<p><b>IP:</b></p>
<input type="text" name="ip" placeholder="127.0.0" />

<input type="submit" value="Submit" name="sub"/>
</form>

<?php echo $result; ?>
</code>
