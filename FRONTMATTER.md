# Hugo Theme - Skye

## Front Matter Configuration

Below is an explanation of the front matter configuration options available.

``` toml
+++
title = "My lovely post"
description = "A description that is shown as a summary on a list page."
date = "2017-07-04T18:44:41+01:00"

author = "Paul Broadwith"
authorbox_top = true
hide_authorbox = false

short_description = "Don't you just love #Hugo?" 

disable_comments = false
draft = false
hide_rss = true
thumbnail = "/images/banner-image.jpg"
thumbnail_css_class = "banner"
thumbnail_caption = 'Image is courtesy of <a href="https://www.flickr.com/photos/aniceflickrprofile" alt="A Nice Flickr Profile Page">A nice profile</a> used under <a href="https://creativecommons.org/licenses/by/2.0/" alt="Creative Commons Attribution 2.0 Generic (CC BY 2.0) licence">Creative Commons Attribution 2.0 Generic (CC BY 2.0)</a> licence.'
thumbnail_hide_list = true

categories = [ "Interesting", "Chocolate" ]
tags = [ "interesting", "chocolate" ]

[[metadata]]
name = "sharing:twitter"
content = "true"

[[metadata]]
name = "sharing:reddit"
content = "/r/hugo"

+++

### author

Name of the author for this article. Note that this must match the name field of a data file in `data/members` (note the name of the data file does not have to match only the name field within it).

```toml
author = "Paul Broadwith" 
```

### authorbox_top

Forces the authorbox to be displayed at the top of the article and not the bottom.

```toml
authorbox_top = true
```
### categories

This is the [standard Hugo front matter][hugo-front-matter-docs] post taxonomies, in this case the post categories.

``` toml
categories = [ "Horses", "Loveliness" ]
``` 

### date

This is the [standard Hugo front matter][hugo-front-matter-docs] date for the post. This can be any date in the past or future. If it is in the future, by default, Hugo will not publish it. You can however overrride this but see the [Hugo documentation][hugo-cli-docs] for that.

``` toml
date = "2017-09-11T17:23:09+00:00"
```

### description

This is the [standard Hugo front matter][hugo-front-matter-docs] description of the post. It's used as a summary description on any list pages the post appears on.

``` toml
description = "The loveliest horse in the whole universe. Ever. Yeah."
```

### disable_comments

If true, this disables the showing of comments on the page or even the comment modules (Disqus, Hashover etc.).

``` toml
disable_comments = true
``` 

### draft

This is the [standard hugo front matter][hugo-front-matter-docs] draft status of the post. If this is true Hugo will not publish the post no matter what the date is. You can overrride this but see the Hugo documentation for that.

``` toml
draft = true
```

### hide_authorbox

If this is true, the authorbox on this post is not shown. There is also a site wide [authorbox configuration][site-config-authorbox] that can be configured.

``` toml
hide_authorbox = true
```

### hide_rss

This will hide the page from the rss feed so that it will not appear in there. You might create a contact 'thankyou' page which will appear in the feed as normal. Using this frontmatter variable will stop it appearing.

``` toml
hide_rss = true
``` 

### metadata

This configuration variable allows you to insert metadata for your content into the <head> tag of the site. Each entry must have the following keys which can contain any valid metadata text:

* name - this is the name tag of the metadata;
* content - this is the content tag of the metadata

The following configuration:

``` toml
[[metadata]]
name = "sharing:twitter"
content = "true"

[[metadata]]
name = "sharing:reddit"
content = "/r/hugo"
```

Will result in the following metadata in the <head> of the site:

``` html
<meta name="sharing:twitter" content="true" />
<meta name="sharing:reddit" content="/r/hugo">
```

### sharing_tweet

Renamed in v0.53 to [twitter_description][#twitter_description].

### tags

This is the [standard Hugo front matter][hugo-front-matter-docs] post taxonomies, in this case the post tags.

``` toml
tags = [ "horses", "loveliness" ]
``` 

### thumbnail

This image is used as the banner for your post. It is shown in the list pages containing the post and in the post itself.

``` toml
thumbnail = "/images/mylovelyhorse.jpg"
```

### thumbnail_css_class

The class to apply to this particular thumbnail image when displayed on the single post. Whatever is contained in this string is put into the `class` attribute.

``` toml
thumbnail_css_class = "banner"
```

Produces this CSS:

``` css
class="post-banner banner"...
```

If this is note set then the class will simply be:

``` css
class="post-banner"...
```

### thumbnail_caption

This is for a caption to be displayed under your thumbnail image on the main post page. Note it does not show on the list page that your post shows on, only on the single post page. I primarily use this for giving attribution to image owners but can be used for any text or HTML.

``` toml
thumbnail_caption = 'Image is courtesy of <a href="https://www.flickr.com/photos/aniceflickrprofile" alt="A Nice Flickr Profile Page">A nice profile</a> used under <a href="https://creativecommons.org/licenses/by/2.0/" alt="Creative Commons Attribution 2.0 Generic (CC BY 2.0) licence">Creative Commons Attribution 2.0 Generic (CC BY 2.0)</a> licence.'
```

``` toml
thumbnail_caption = "This is my lovely lovely horse!"
```

### thumbnail_hide_list

This allows the page thumbnail to be hidden from list pages.

``` toml
thumbnail_hide_list = true
```

### title

This is the [standard Hugo front matter][hugo-front-matter-docs] title for the post. It's used in the thumbnail image as the `alt` tag, the page body `title` and the title for social media such as Facebook and Twitter. Make this keyword rich.

``` toml
title = "My lovely horse"
```

### twitter_description

This is what will be used in the twitter:description of your [Twitter card][twitter-card-summary] and will be used if your post is shared using the sharing button. If this field is not present then the [description][#description] will be used instead. Was previously called [sharing_tweet][#sharing_tweet.]

``` toml
twitter_description = "Don't you just love #Hugo?"
```

[hugo-cli-docs]: https://gohugo.io/overview/usage/ "Using Hugo"
[hugo-front-matter-docs]: https://gohugo.io/content/front-matter/ "Hugo Front Matter"
[site-config-authorbox]: CONFIGURATION.md#authorbox
[twitter-card-summary]: https://dev.twitter.com/cards/types/summary "Twitter Developer Documentation - Summary card"