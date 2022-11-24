# WordPress Settings API Class

Allows for easier creation of plugin settings pages by using an object orianted approach, with an API similar to the customizer.

## An example

```
$settings = new SettingsApi(
	'Plugin Settings',
	'Plugin Settings',
	'manage_options',
	'plugin-name'
);

// Section: Basic Settings.
$settings->add_section(
	[
		'id'    => 'plugin_name_basic',
		'title' => __( 'Basic Settings', 'plugin-name' ),
	]
);

// Section: Other Settings.
$settings->add_section(
	[
		'id'    => 'plugin_name_other',
		'title' => __( 'Other Settings', 'plugin-name' ),
	]
);

// Field: Text.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'      => 'text',
		'type'    => 'text',
		'name'    => __( 'Text Input', 'plugin-name' ),
		'desc'    => __( 'Text input description', 'plugin-name' ),
		'default' => 'Default Text',
	]
);

// Field: Number.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'                => 'text_no',
		'type'              => 'number',
		'name'              => __( 'Number Input', 'plugin-name' ),
		'desc'              => __( 'Number field with validation callback `intval`', 'plugin-name' ),
		'default'           => 1,
		'sanitize_callback' => 'intval',
	]
);

// Field: Email.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'   => 'email',
		'type' => 'email',
		'name' => __( 'Email', 'plugin-name' ),
		'desc' => __( 'Email field description', 'plugin-name' ),
	]
);

// Field: Password.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'   => 'password',
		'type' => 'password',
		'name' => __( 'Password Input', 'plugin-name' ),
		'desc' => __( 'Password field description', 'plugin-name' ),
	]
);

// Field: Textarea.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'   => 'textarea',
		'type' => 'textarea',
		'name' => __( 'Textarea Input', 'plugin-name' ),
		'desc' => __( 'Textarea description', 'plugin-name' ),
	]
);

// Field: Separator.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'   => 'separator',
		'type' => 'separator',
	]
);

// Field: Title.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'   => 'title',
		'type' => 'title',
		'name' => '<h1>Title</h1>',
	]
);

// Field: Checkbox.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'   => 'checkbox',
		'type' => 'checkbox',
		'name' => __( 'Checkbox', 'plugin-name' ),
		'desc' => __( 'Checkbox Label', 'plugin-name' ),
	]
);

// Field: Radio.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'      => 'radio',
		'type'    => 'radio',
		'name'    => __( 'Radio', 'plugin-name' ),
		'desc'    => __( 'Radio Button', 'plugin-name' ),
		'options' => [
			'yes' => 'Yes',
			'no'  => 'No',
		],
	]
);

// Field: Multicheck.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'      => 'multicheck',
		'type'    => 'multicheck',
		'name'    => __( 'Multile checkbox', 'plugin-name' ),
		'desc'    => __( 'Multile checkbox description', 'plugin-name' ),
		'options' => [
			'yes' => 'Yes',
			'no'  => 'No',
		],
	]
);

// Field: Select.
$settings->add_field(
	'plugin_name_basic',
	[
		'id'      => 'select',
		'type'    => 'select',
		'name'    => __( 'A Dropdown', 'plugin-name' ),
		'desc'    => __( 'A Dropdown description', 'plugin-name' ),
		'options' => [
			'yes' => 'Yes',
			'no'  => 'No',
		],
	]
);

// Field: Image.
$settings->add_field(
	'plugin_name_other',
	[
		'id'      => 'image',
		'type'    => 'image',
		'name'    => __( 'Image', 'plugin-name' ),
		'desc'    => __( 'Image description', 'plugin-name' ),
		'options' => [
			'button_label' => 'Choose Image',
		],
	]
);

// Field: File.
$settings->add_field(
	'plugin_name_other',
	[
		'id'      => 'file',
		'type'    => 'file',
		'name'    => __( 'File', 'plugin-name' ),
		'desc'    => __( 'File description', 'plugin-name' ),
		'options' => [
			'button_label' => 'Choose file',
		],
	]
);

// Field: Color.
$settings->add_field(
	'plugin_name_other',
	[
		'id'          => 'color',
		'type'        => 'color',
		'name'        => __( 'Color', 'plugin-name' ),
		'desc'        => __( 'Color description', 'plugin-name' ),
		'placeholder' => __( '#5F4B8B', 'plugin-name' ),
	]
);

// Field: WYSIWYG.
$settings->add_field(
	'plugin_name_other',
	[
		'id'   => 'wysiwyg',
		'type' => 'wysiwyg',
		'name' => __( 'WP_Editor', 'plugin-name' ),
		'desc' => __( 'WP_Editor description', 'plugin-name' ),
	]
);
```

## Credits

Heavily based on [WP-OOP-Settings-API](https://github.com/ahmadawais/WP-OOP-Settings-API) by Ahmad Awais.
