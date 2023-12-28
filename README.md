# send-email
this package to facilitate the creation of the email and send it 


> composer require crazy-email-package/send-email

>php artisan vendor:publish --provider="CrazyEmailPackage\SendEmail\CrazySendMailServiceProvider"

```json
Route::any('/crazy_email', [SendMailController::class, 'send_mail'])->name('crazy_email.send_mail');


```

this is the route for sending the email 

```javascript

<!-- Include jQuery -->
<script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>

<script>
    $(document).ready(function () {
        $('#sendEmailButton').click(function () {
            // Get form data or create an object with the required parameters
            var mailData = {
                sender_email: "sender@example.com",
                receiver_email: "receiver@example.com",
                subject: "Test Email",
                body: "This is a test email.",
                logo: "path/to/logo.png"
            };

            var viewPath = "emails_templates.mail_notify";

            // Make Ajax request
            $.ajax({
                type: 'POST',
                url: '/crazy_email',
                contentType: 'application/json',
                data: JSON.stringify({
                    mailData: mailData,
                    view_path: viewPath
                }),
                success: function (response) {
                    console.log(response);
                    // Handle success response
                },
                error: function (error) {
                    console.error(error);
                    // Handle error response
                }
            });
        });
    });
</script>


```