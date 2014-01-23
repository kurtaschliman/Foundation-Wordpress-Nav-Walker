Foundation-Wordpress-Nav-Walker
===============================

A WordPress Nav Walker for Foundation 5

Installation: place this file in your WordPress theme and include it in functions.php.  

For example, with the file located here:

Theme
├── inc/foundation-nav-walker.php

Add the following to functions.php:

require get_template_directory() . '/inc/foundation-walker.php';

Then when calling wp_nav_menu, simply pass a the Foundation class as the walker:

<?php wp_nav_menu( array(
					'theme_location'  => '',
	        'menu'            => '',
	        'container'       => 'div',
	        'container_class' => '',
	        'container_id'    => '',
	        'menu_class'      => 'button-group',
	        'menu_id'         => '',
	        'echo'            => true,
	        'fallback_cb'     => 'wp_page_menu',
	        'before'          => '',
	        'after'           => '',
	        'link_before'     => '',
	        'link_after'      => '',
	        'items_wrap'      => '<ul id="%1$s" class="%2$s">%3$s</ul>',
	        'depth'           => 0,
					'walker'          => new Foundation_Walker_Nav_Menu() 
	  		) 
		  ); 
?>
