# ACF Icon Selector Field

Allows you to create an 'icon-picker' acf-field.

This is a fork of houke/acf-icon-picker to fix issues like the background color and REST API response format

## Installation

### via Composer

1. Add a line to your repositories array: `{ "type": "github", "url": "https://github.com/TimeZHero/acf-icon-picker" }`
2. Add a line to your require block: `"timezhero/acf-icon-picker"`
3. Run `composer update`

### Manually

1. Copy the `acf-icon-picker` folder into your `wp-content/plugins` folder
2. Activate the Icon Selector plugin via the plugins admin page

## Filters

Use the below filters to override the default icon folder, path, and / or URL:

```php
// modify the path to the icons directory
add_filter('acf_icon_path_suffix', 'acf_icon_path_suffix');

function acf_icon_path_suffix($path_suffix) {
    return 'assets/img/icons/';
}

// modify the path to the above prefix
add_filter('acf_icon_path', 'acf_icon_path');

function acf_icon_path($path_suffix) {
    return plugin_dir_path( __FILE__ );
}

// modify the URL to the icons directory to display on the page
add_filter('acf_icon_url', 'acf_icon_url');

function acf_icon_url($path_suffix) {
    return plugin_dir_url(__FILE__);
}
```

For Sage/Bedrock edit filters.php:

```php
/// modify the path to the icons directory
add_filter('acf_icon_path_suffix', function ($path_suffix) {
    return '/assets/images/icons/'; // After assets folder you can define folder structure
});

// modify the path to the above prefix
add_filter('acf_icon_path', function ($path_suffix) {
    return '/app/public/web/themes/THEME_NAME/resources';
});

// modify the URL to the icons directory to display on the page
add_filter('acf_icon_url', function ($path_suffix) {
    return get_stylesheet_directory_uri();
});
```

## Screenshots

![Icon Picker](https://raw.githubusercontent.com/houke/acf-icon-picker/master/screenshots/example.png)
