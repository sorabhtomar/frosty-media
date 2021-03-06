Frosty Media (License Manager)
============

The core functionallity that manages all Frosty.Media licenses, settings, auto-updates and notifications. It's a required plugin for any purchases made on [Frosty Media](http://frosty.media).

### Usage

Download zip and install, or as a standalone include. (Download and install is required for all [Frosty Media](http://frosty.media) purchased plugins. 

Use the function below inside your plugin you need licensed and managed.

```php
/**
 * Register our plugin for license management.
 *
 * @return 	array plugins
 */
function frosty_media_register_licensed_plugin( $plugins ) {
	
	$plugins[] = array(
		'id' 			=> 'prefix_plugin_title', // Option title
		'title' 		=> 'Plugin Title', // Must match EDD post_title!
		'version'		=> '1.0.0',
		'file'			=> __FILE__,
		'basename'		=> plugin_basename( __FILE__ ),
		'download_id'	=> '2345', // EDD download ID!
		'author'		=> 'Austin Passy' // Author of this plugin
	);	
	return $plugins;
}
add_filter( 'frosty_media_add_plugin_license', 'frosty_media_register_licensed_plugin' );
```

### Changelog

~Current Version:1.1.0~

##### Version 1.1.0 *10/10/15*
* Code rewrite and cleanup.
* Introduced namespaced code.
* Fixed messages not showing up.
* Fixed license key activation errors.

##### Version 1.0.9 *01/27/15*
* Fix: issue #2 - unexpected T_FUNCTION (PHP versions < 5.3).

##### Version 1.0.8 *01/11/15*
* Double check notices aren't NULL.
* Fix: licenses sending empty license_key.

##### Version 1.0.7 *01/05/15*
* Fix: license activation update overwriting the settings array.

##### Version 1.0.6 *01/05/15*
* Proper deactivation and reactivation of plugin after GitHub folder rename.
* Fix: GitHub issue #1.

##### Version 1.0.5 *12/12/14*
* Rename folder if installed via GitHub zipball.

##### Version 1.0.4 *12/12/14*
* Fix: Possible empty array in notifications on first activation.

##### Version 1.0.3 *12/12/14*
* Added FM_Common static class.
* Cleaned up code.

##### Version 1.0.2 *12/08/14*
* Update FM_API_URL to https.
* Updated EDD_SL_Plugin_Updater.php to version 1.5.

##### Version 1.0.1 *11/14/14*
* Added: edd-sl-api/ enpoint to license API URL.

##### Version 1.0.0 *11/11/14*
* Initial Release.