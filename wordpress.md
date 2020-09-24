1.Thêm Edit (Classic) đơn giản mà không cần dùng Plugin
add_action( 'plugins_loaded', 'classic_editor_init_actions' );
function classic_editor_init_actions() {
	$gutenberg = false;
	if ( isset( $_GET['classic-editor'] ) ) {
		add_filter( 'use_block_editor_for_post_type', '__return_false', 100 );
	}
	add_filter( 'page_row_actions', 'classic_editor_add_edit_links', 15, 2 );
	add_filter( 'post_row_actions', 'classic_editor_add_edit_links', 15, 2 );
	if ( ! $gutenberg ) {
		add_filter( 'redirect_post_location', 'classic_editor_redirect_location' );
	}
}
function classic_editor_redirect_location( $location ) {
	if (
		isset( $_REQUEST['classic-editor'] ) ||
		( isset( $_POST['_wp_http_referer'] ) && strpos( $_POST['_wp_http_referer'], '&classic-editor' ) !== false )
	) {
		$location = add_query_arg( 'classic-editor', '', $location );
	}
	return $location;
}
function classic_editor_add_edit_links( $actions, $post ) {
	if ( 'trash' === $post->post_status || ! post_type_supports( $post->post_type, 'editor' ) ) {
		return $actions;
	}
	$edit_url = get_edit_post_link( $post->ID, 'raw' );
	if ( ! $edit_url ) {
		return $actions;
	}
	$edit_url = add_query_arg( 'classic-editor', '', $edit_url );
	$title       = _draft_or_post_title( $post->ID );
	$edit_action = array(
		'classic' => sprintf(
			'<a href="%s" aria-label="%s">%s</a>',
			esc_url( $edit_url ),
			esc_attr( sprintf(
				__( 'Edit &#8220;%s&#8221; in the classic editor', 'classic-editor' ),
				$title
			) ),
			__( 'Edit (Classic)', 'classic-editor' )
		),
	);
	$edit_offset = array_search( 'edit', array_keys( $actions ), true );
	array_splice( $actions, $edit_offset + 1, 0, $edit_action );
	return $actions;
}

2.Ẩn plugin không cho người khác thấy
function wpvn_hide_plugin() {
  global $wp_list_table;
  $hidearr = array('woocommerce/woocommerce.php'); //Link plugin
  $myplugins = $wp_list_table->items;
  foreach ($myplugins as $key => $val) {
    if (in_array($key,$hidearr)) {
      unset($wp_list_table->items[$key]);
    }
  }
}
add_action('pre_current_active_plugins', 'wpvn_hide_plugin');
