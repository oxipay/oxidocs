#HTML Generation Sample Code

Below is a code snippet that demonstrates how the webpage that posts to Certegy might be generated:

```php
private function postToCheckout($checkoutUrl, $payload)
{
	echo
	"<html>
		<body>
		<form id='form' action='$checkoutUrl' method='post'>";
	foreach ($payload as $key => $value) {
		echo "<input type='hidden' id='$key' name='$key' value='$value'/>";
	}
	echo
	'</form>
		</body>';
	echo
	'<script>
		var form = document.getElementById("form");
		form.submit();
	</script>
	</html>';
}
```