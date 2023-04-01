# Elementor
Custom Widgets and Addon CUstomizations

- How to create Custom Widget with Input fields and front end output in Elementor
- Modifying Existing Elementor Addons to acheive any specific functionality
- Usage of hooks to modify Elementor Widget via theme fucntions.php


Hooks to call custom widgets in your theme functions

// elementor widget to ggrab all partners info

add_action('init', function(){
	if(did_action('elementor/loaded')){
		require_once __DIR__ . '/elementor_templates/elementor_all_partner_widget.php';
		\Elementor\Plugin::instance()->widgets_manager->register_widget_type( new ElementorPostswidget() );
	}
	
});



// elementor widget to ggrab single partners info

add_action('init', function(){
	if(did_action('elementor/loaded')){
		require_once __DIR__ . '/elementor_templates/elementor_single_partner_widget.php';
		\Elementor\Plugin::instance()->widgets_manager->register_widget_type( new ElementorPartnerswidget() );
	}
	
});
