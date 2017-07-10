# Hugo Theme - Skye

## Front Matter Configuration

Below is an explanation of the front matter configuration options available.

``` toml
+++
title = "My lovely post"
description = "A description that is shown as a summary on a list page."
date = "2017-07-04T18:44:41+01:00"

disable_comments = false
draft = false
hide_authorbox = false
thumbnail = "/images/banner-image.jpg"
thumbnail_caption = 'Image is courtesy of <a href="https://www.flickr.com/photos/aniceflickrprofile" alt="A Nice Flickr Profile Page">A nice profile</a> used under <a href="https://creativecommons.org/licenses/by/2.0/" alt="Creative Commons Attribution 2.0 Generic (CC BY 2.0) licence">Creative Commons Attribution 2.0 Generic (CC BY 2.0)</a> licence.'

categories = [ "Interesting", "Chocolate" ]
tags = [ "interesting", "chocolate" ]

+++
```

### title

This is the [standard Hugo front matter][hugo-front-matter-docs] title for the post. It's used in the thumbnail image as the `alt` tag, the page body `title` and the title for social media such as Facebook and Twitter. Make this keyword rich.

``` toml
title = "My lovely horse"
```

### description

This is the [standard Hugo front matter][hugo-front-matter-docs] description of the post. It's used as a summary description on any list pages the post appears on.

``` toml
description = "The loveliest horse in the whole universe. Ever. Yeah."
```

### date

This is the [standard Hugo front matter][hugo-front-matter-docs] date for the post. This can be any date in the past or future. If it is in the future, by default, Hugo will not publish it. You can however overrride this but see the [Hugo documentation][hugo-cli-docs] for that.

``` toml
date = "2017-09-11T17:23:09+00:00"
```

### disable_comments

If true, this disables the showing of comments on the page or even the comment modules (Disques, Hashover etc.).

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

### thumbnail

This image is used as the banner for your post. It is shown in the list pages containing the post and in the post itself.

``` toml
thumbnail = "/images/mylovelyhorse.jpg"
```

### thumbnail_caption 

This is for a caption to be displayed under your thumbnail image on the main post page. Note it does not show on the list page that your post shows on, only on the single post page. I primarily use this for giving attribution to image owners but can be used for any text or HTML.

``` toml
thumbnail_caption = 'Image is courtesy of <a href="https://www.flickr.com/photos/aniceflickrprofile" alt="A Nice Flickr Profile Page">A nice profile</a> used under <a href="https://creativecommons.org/licenses/by/2.0/" alt="Creative Commons Attribution 2.0 Generic (CC BY 2.0) licence">Creative Commons Attribution 2.0 Generic (CC BY 2.0)</a> licence.'
```

``` toml
thumbnail_caption = "This is my lovely lovely horse!"
```

### categories

This is the [standard Hugo front matter][hugo-front-matter-docs] post taxonomies, in this case the post categories.

``` toml
categories = [ "Horses", "Loveliness" ]
``` 

### tags


This is the [standard Hugo front matter][hugo-front-matter-docs] post taxonomies, in this case the post tags.

``` toml
categories = [ "horses", "loveliness" ]
``` 

[hugo-cli-docs]: https://gohugo.io/overview/usage/ "Using Hugo"
[hugo-front-matter-docs]: https://gohugo.io/content/front-matter/ "Hugo Front Matter"
[site-config-authorbox]: CONFIGURATION.md#authorbox