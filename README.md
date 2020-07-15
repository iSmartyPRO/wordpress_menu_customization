# Description
Wordpress Menu Customization for User Role


# HowTo

Add following code into functions.php for hide some menu items to Shop Manager user role.
Depend on your requirements you can customize role name in code  .

```
    function remove_menus(){
        // get current login user's role
        $roles = wp_get_current_user()->roles;
         
        // test role
        if( !in_array('shop_manager',$roles)){
        return;
        }
         
        //remove menu from site backend.
        remove_menu_page('edit.php' ); //Posts
        remove_menu_page('edit-comments.php' ); //Comments
        remove_menu_page('themes.php' ); //Appearance
        remove_menu_page('plugins.php' ); //Plugins
        remove_menu_page('users.php' ); //Users
        remove_menu_page('tools.php' ); //Tools
        remove_menu_page('profile.php' ); //Settings
        remove_menu_page('edit.php?post_type=testimonials'); // Testimonials
        remove_menu_page('edit.php?post_type=etheme_portfolio'); // Portfolio
        }
        add_action( 'admin_menu', 'remove_menus' , 100 );
```
