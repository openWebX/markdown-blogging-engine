# markdown-blogging-engine
A simple file based blogging system.  

## Changelog
### v 1.0
* added `$posts->get_archive()`
* added `archive.php`
	* now `template/YOURTEMPLATE/archive.php` is required. [Sample Code](./template/simple/archive.php)

### v 0.9.1
* [`$post->timestamp` is now a real Timestamp, no `DateTime`-Thing anymore](https://github.com/lukasepple/markdown-blogging-engine/commit/7a74aee0e0bf3b88e80cdcd621dd3cf0d7d97f6f)
* [You are able to configure your timezone](https://github.com/lukasepple/markdown-blogging-engine/commit/7a74aee0e0bf3b88e80cdcd621dd3cf0d7d97f6f#L2R2)
* [`$post->filename` was added](https://github.com/lukasepple/markdown-blogging-engine/commit/490ac32af904eb9aa27541e791a8275ab228c2ac)
* [Security issue closed](https://github.com/lukasepple/markdown-blogging-engine/commit/e249fe57da50e98c1fd5da6298800f1c40315d88)
* Moved config.php to config.sample.php (See Installation)
* Moved .htaccess to htaccess.txt (See Installation)
* [Post that are dated to the future are published in the future now.](https://github.com/lukasepple/markdown-blogging-engine/commit/3fc5f71e7064f1da423173e145bf120175158d51)

### v 0.9  
Added Support for Pagination:  
`$posts->get_all($page, $max_posts_per_page)` expects now two paramenters. (`$page` is provided as `$page` already).  
Add Pagination like that:  
```
echo "<p>";
if($page != 1){
	echo "<a href=\"./?page=". ($page - 1) ."\">Newer</a> &ndash; ";
}
echo "<a href='./?page=". ($page + 1) ."'>Older</a>";
echo "</p>";
```
## Installation
* Upload everything to your server
* move `system/config.sample.php` to `system/config.php`
* edit `system/config.php`
	* change your timezone
	* change `BASE_URL` to the Base url of your installation
	* change `BLOG_NAME`
	* If you want locate your post otherwhere and change `POST_DIR`
	* Your `TEMPLATE` is the name of the folder, like `simple`
	* `TWITTER`and `MAIL`are clear, aren't they.
* move `htaccess.txt` to `.htaccess`
* edit `.htaccess`
	* change `RewriteBase` to `RewriteBase /path/to/your/blog`

## Add a post
* place a file in your `POST_DIR`
* naming convention: my-title.md
* Then write:    

```markdown
Title
- YYYY-MM-TT hh:mm
my awesome content
```

## I want WYSIWYG!
Awesome [markuman](https://github.com/markuman/mbe-writer) wrote [mbe-writer](https://github.com/markuman/mbe-writer)! Now your life is (maybe) better!

## Create own templates
[I wrote some documentation!](https://github.com/lukasepple/markdown-blogging-engine/wiki)
## lighttpd
[Config by markuman](https://github.com/lukasepple/markdown-blogging-engine/issues/2)
