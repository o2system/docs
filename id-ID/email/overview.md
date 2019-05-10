# Email

O2System menyediakan API yang bersih dan sederhana dengan driver untuk SMTP, Mailgun, dan `sengrid`. Berikut ini merupakan contoh dasar bagaimana mengirim Email di O2System.

```php
$message = new Mail\Message();
$message->contentType( 'html' );
$message->from( 'steevenz@ymail.com', 'Me' );
$message->subject( 'Testing email protocol encoding with attachment' );
$message->body( 'Testing mail body' );
$message->to( 'steeven.lim@gmail.com', 'Steeven Lim' );
$message->priority( Mail\Message::PRIORITY_HIGHEST );

$message->addAttachment( PATH_STORAGE . 'images/ferrari.jpg' );
```

## Pengaturan Preferensi Email


```php
<?php
/**
 * Email Configuration
 *
 * @var \O2System\Email\DataStructures\Config
 */
$email = new \O2System\Email\DataStructures\Config([
    /**
     * Sender Protocol
     * Supported sender protocol mail, smtp or sendmail.
     *
     * @var string
     */
    'protocol' => 'mail',

    /**
     * Sender User Agent
     *
     * @var string
     */
    'userAgent' => 'O2System\Email',

    /**
     * Wordwrap email body.
     *
     * @var bool
     */
    'wordwrap' => false,

    // ------------------------------------------------------------------------

    /**
     * SendMail Protocol Configuration
     * Set sendmail binary path.
     *
     * @var string
     */
    'mailPath' => '/usr/sbin/sendmail',

    /**
     * SMTP Protocol Configuration
     * Fill all configuration below if you set protocol to smtp.
     */

    // ------------------------------------------------------------------------

    /**
     * SMTP Host
     * Can be an IP Address or domain name.
     *
     * @var string
     */
    'host' => '',

    /**
     * SMTP Port
     * By default it's set to 25.
     *
     * @var numeric
     */
    'port' => 25,

    /**
     * SMTP Username
     *
     * @var string
     */
    'user' => '',

    /**
     * SMTP Password
     *
     * @var string
     */
    'pass' => '',

    /**
     * SMTP Encryption Type
     * Supported encryption type tls or ssl.
     *
     * @var string
     */
    'encryption' => ''
]);
```