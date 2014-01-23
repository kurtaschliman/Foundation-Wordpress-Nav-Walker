Foundation 5 Wordpress Nav Walker
===============================

A custom WordPress Nav Walker for Zurb Foundation 5

*When looking for a good Foundation 5 nav walker, I found [this thread](http://foundation.zurb.com/forum/posts/438-enabling-foundation-5-nav-with-wordpress-menus) but not many repositories to reference.  So I thought I would share my code for anyone else in my shoes, searching GitHub for the answer.  This code is heavily influenced by that thread and the wp-includes/nav-menu-template.php file in the WordPress core.*

## Installation 
Place the foundation-nav-walker.php file in your WordPress theme and include it in functions.php.  

For example, with the file located here:

```
Theme
├── inc
    ├── foundation-nav-walker.php
```

Add the following to functions.php:

``` PHP
require get_template_directory() . '/inc/foundation-walker.php';
```

Then when calling wp_nav_menu, simply pass a the Foundation class as the walker:

``` PHP

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
```
