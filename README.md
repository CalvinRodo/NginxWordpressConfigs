NginxWordpressConfigs
=====================

My config files for getting Wordpress working on nginx

These config files are based off of the ones found on the wordpress site. 
[Link to original article](http://codex.wordpress.org/Nginx)

**restrictions.conf**

This is the Global restrictions file

**multisite_wordpress.conf**

For multisite subdirectory installations.
This configuration may also work for subdomain installations without modification. This configuration may also work for a single blog installation (non-network/multisite).

**wpsupercache.conf**

Wordpress Super Cache rules.

**w3tcbrowsercache.conf**

If you don't have the static gzip module compiled in, be sure to comment out the correct line.

**Notes**

A couple last notes: This whole setup assumes that the root of the site is the blog and that all files that will be referenced reside on the host. If you put the blog in a subdirectory such as /blog, then the rules will unfortunately have to be modified to handle that situation. Perhaps someone can take these rules and make it possible to, for instance, use a:

set $wp_subdir "/blog";
Directive in the main 'server' block and have it automagically apply to the generic WP rules.

**Warning**

If you have a symlink to your uploaded files in wp-content/cache/ please change them to wp-content/ms-filemap/ and change the rewrite rule as mention above. Your caching plugin will probably delete all your uploaded files if that link is still there.
