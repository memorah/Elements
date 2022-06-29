A short description of the product below the photo on the store's website
---
```php
dd_action( 'woocommerce_after_shop_loop_item_title', 'wc_add_short_description' );

function wc_add_short_description() {
	global $product;

	?>
        <div itemprop="description">
            <?php echo apply_filters( 'woocommerce_short_description', $product->post-> post_excerpt ) ?>
        </div>
}
``` 
