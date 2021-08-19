# WordPress SMTP Mail
### Step 1: Goto your wp-config.php file and below code and change yours:

```
define( 'SMTP_USER',   'user@example.com' );    // Username to use for SMTP authentication
define( 'SMTP_PASS',   'smtp password' );       // Password to use for SMTP authentication
define( 'SMTP_HOST',   'smtp.example.com' );    // The hostname of the mail server
define( 'SMTP_FROM',   'website@example.com' ); // SMTP From email address
define( 'SMTP_NAME',   'e.g Website Name' );    // SMTP From name
define( 'SMTP_PORT',   '25' );                  // SMTP port number - likely to be 25, 465 or 587
define( 'SMTP_SECURE', 'tls' );                 // Encryption system to use - ssl or tls
define( 'SMTP_AUTH',    true );                 // Use SMTP authentication (true|false)
define( 'SMTP_DEBUG',   0 );                    // for debugging purposes only set to 1 or 2
```
### Step 2: This will work if this code apply in function.php or custom plugin:

```
add_action( 'phpmailer_init', 'send_smtp_email' );
function send_smtp_email( $phpmailer ) {
	$phpmailer->isSMTP();
	$phpmailer->Host       = SMTP_HOST;
	$phpmailer->SMTPAuth   = SMTP_AUTH;
	$phpmailer->Port       = SMTP_PORT;
	$phpmailer->Username   = SMTP_USER;
	$phpmailer->Password   = SMTP_PASS;
	$phpmailer->SMTPSecure = SMTP_SECURE;
	$phpmailer->From       = SMTP_FROM;
	$phpmailer->FromName   = SMTP_NAME;
}
```
### Done!
