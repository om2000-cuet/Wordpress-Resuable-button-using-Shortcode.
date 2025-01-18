# Wordpress-Resuable-button-using-Shortcode.
A button shortcode which will take URL and Button Label as parameter and is obviously reusable.
So to use same button in different post or pages with different url and button label, this [button] shortcode will help you. Just put the following code in function.php and use it as follows
[button url="https://google.com" label="Google"]
or
[button url="https://yahoo.com" label ="Yahoo"]

Here is the code



    function customized_button( $attributes ) {
    $url = $attributes[ 'url' ];
    $label = $attributes[ 'label' ];

    // Add CSS inline with the button
    $css = "
        <style>
            .custom-button {
                display: inline-block;
                padding: 10px 20px;
                background-color: #2271b1;
                color: #ffffff;
                text-decoration: none !important;
                border-radius: 4px;
                font-weight: 500;
                transition: all 0.3s ease;
            }
            .custom-button:hover {
                background-color: #135e96;
                color: #ffffff;
                transform: translateY(-2px);
            }
        </style>
    ";
    return $css.sprintf( "<a target='_blank' class='custom-button' href='%s'>%s</a>", $url, $label );
    }
    add_shortcode( 'button', 'customized_button' );


