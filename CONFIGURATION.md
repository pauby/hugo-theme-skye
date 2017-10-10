# Hugo Theme - Skye

## Site Wide Configuration - [Params]

### tagline

At the top of each page is a site header containing the name of the website in
large letters and, if a tagline is specified, the tagline in smaller letters
underneath the site's name:

``` toml
tagline = "This is my site's tagline" # Subtitle of your site
```

### description

Site descrioption that appears in search engines.

``` toml
description = "Here is a description of my site that will appear in search engine results - W00t!"
```

### cover

Site wide cover image used by OpenGraph as `og:image` property. Within content the value of the `image` variable is used.

``` toml
cover = "/images/cover.jpg"
```

### authorbox

The authorbox provides attribution to the author of a given post. To enable
authorboxes sitewide, include the line `authorbox = true` under `[Params]`
in `config.toml`.

You can also override the sitewide setting by setting `authorbox` in the front
matter of a piece of content.

To display a person's information in the authorbox, you need two more things.
First, a data file under `/data/members/` that has the following information:

```toml
Name = "Luke Skywalker"
Img = "/path/to/picture/of/lukeskywalker.jpg"
Position = "Master Jedi"
Bio = "I'm Luke. My father tried to kill me and then saved me. I'm confused."
```

And then the [author](#author) variable set to a `name` in the data file.

### author

On the page you are attributing to a person, set the `author` variable
to the same value as `name` in a data file. As long as authorboxes are enabled for the page, either sitewide or on a post, the authorbox will be displayed at the bottom of the page.

``` toml
author = "Luke Skyewalker"
```

### authorbox_top

Forces the authorbox to be displayed at the top of the article and not the bottom.

```toml
authorbox_top = true
```

### post_navigation

This variable control whether navigation to previous / next posts will be displayed at the bottom of the current post. To turn on, set to `true` and to turn off set to `false`.

``` toml
post_navigation = false
```

### hashover

Controls whether the site uses [Hashover](http://tildehash.com/?page=hashover) commenting system or not. To turn it on, set to `true` and the Hashover CSS and code will be included on the site. If you are using a different commenting system or don't want to use comments on your posts set this to `false`.

``` toml
hashover = false
```

### RSSLink

The URL for your site RSS feed.

``` toml
RSSLink = "http://feeds.specificfeeds.com/pauby"
```

### rss_disable_summary

The theme comes with it's own RSS template which is a slightly modified version of [Hugo's embedded RSS template](https://gohugo.io/templates/rss/#the-embedded-rss-xml). The modification allows the page description, as specified in the [front matter](FRONTMATTER.md#description), to be used instead of the page summary. 

``` toml
rss_disable_summary = true
```

### GoogleAnalyticsUserID

Enter your Google Analytics User ID here to allow site stats to be collected. If this variable is not present or you are running on localhost not analytics will be collected.

``` toml
GoogleAnalyticsUserID = "AB-12345678-1"
```

### custom_css

This array allows you to add CSS files your site without the need to edit any files. When creating the pages for your site each URL you place in here is wrapped in  `<link rel="stylesheet" type="text/css" href="...">` and included at the end of the `<head>` section of your page. For example, this variable:

``` toml
custom_css = [ "/css/mystyles.css", "//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.6.0/styles/default.min.css"]
```

Will result in this code within the `<head>` section of the page:

``` html
...
<head>
  ...
  <link rel="stylesheet" type="text/css" href="/css/mystyles.css">
  <link rel="stylesheet" type="text/css" href="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.6.0/styles/default.min.css">
  ...
</head>
```

### custom_js_head

This array allows you to add Javascript files your site without the need to edit any files. When creating the pages for your site each URL you place in here is wrapped in  `<script src="..." ></script>` and included at the end of the `<head>` section of your page. For example, this variable:

``` toml
custom_js_head = [ "/js/myjavascript.js", "//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.6.0/highlight.min.js"]
```

Will result in this code within the `<head>` section of the page:

``` html
...
<head>
  ...
  <script src="/js/myjavascript.js"></script>
  <script src="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.6.0/highlight.min.js"></script>
  ...
</head>
```

### custom_js_foot

This array allows you to add Javascript files your site without the need to edit any files. When creating the pages for your site each URL you place in here is wrapped in  `<script src="..." ></script>` and included just before the `</body>` tag on your page. For example, this variable:

``` toml
custom_js_foot = [ "/js/myjavascript.js", "//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.6.0/highlight.min.js"]
```

Will result in this code within just before the `</body>` tag on the page:

``` html
  ...
  <script src="/js/myjavascript.js"></script>
  <script src="//cdnjs.cloudflare.com/ajax/libs/highlight.js/9.6.0/highlight.min.js"></script>
  ...
</body>
```

### fontawesome

Controls whether Font Awesome CSS is included in the page <head>.

If this is true and [fontawesome_cdn_embedcode](#fontawesome_cdn_embedcode) is empty then as per the [Font Awesome Getting Started instructions](http://fontawesome.io/get-started/), the `css/font-awesome.min.css` is included from the head (make sure this file is placed in the correct location).

If this is true and [fontawesome_cdn_embedcode][#fontawesome_cdn_embedcode] is not an empty value, then as per the [Font Awesome Getting Started instructions](http://fontawesome.io/get-started/), the `<script src="https://use.fontawesome.com/<YOUR CDN EMBED CODE>.js"></script>` is included in the `<head>` section.

``` toml
fontawesome = true
fontawesome_cdn_embedcode = "1234567890"
```

Will result in the following HTML being aded to the `<head>`:

``` html
<script src="https://use.fontawesome.com/1234567890.js"></script>
```

### fontawesome_cdn_embedcode

This is your [Font Awesome CDN Embed Code](http://fontawesome.io/get-started/). If you prefer to use the local CSS on your site for this then remove this or leave the value blank.

See [fontawesome](#fontawesome) for more information.

## Configuration - [Params.Footer]

### copyright

Whatever text is in this configuration vakue is displayed in the footer. Normally used for site copyright text, hence the name. The text can include normal markdown.

``` toml 
copyright = "&copy; My awesome site 2017. Powered by Hugo."
```

## Configuration - [Params.Fonts]

This section is for configuration of the sites fonts.

### code_font

The font used for the code text on your site within `<pre>` or `<code>` blocks.

``` toml
code_font = "Courier New"
```

Produces this CSS code:

``` css
code, pre {
  font-family: Courier New, monospace !important;
}
```

This will use the Courier New font for code text. Note that whatever you put here will have `monospace` added as the final fallback font should none of the others be available.

See the `index.css` for config variables and `reset.css` for the CSS.

### default_font

The font used for the site by default.

``` toml
default_font = "Arial"
```

Produces this CSS code:

``` css
body {
  font-family: Arial, sans-serif;
}
```

This will use the Arial font for all site text (without specific styling). 

See the `index.css` for config variables and `reset.css` for the CSS.

### googlefonts

This controls the [Google Fonts](https://fonts.google.com/) that are loaded with your site.

``` toml
googlefonts = [ "Bitter", "Source+Sans+Pro" ]
```

This will load the Bitter and Source Sans Pro fonts. Note that **any spaces in your font name must be replaced by +** or the font may not be loaded.

See the `header.html` for the code.

###	post_header_font

The font used for the `h1` to `h6` headers on your site.

``` toml
post_header_font = "Bitter, Source Sans Pro"
```

Produces this CSS code:

``` css
#post-article h1 ... #post-article h6 {
  font-family: Bitter, Source Sans Pro, sans-serif;
}
```

This will use the Bitter, then the Source Sans Pro font for the `h` headers. Note that whatever you put here will have sans-serif added as the final fallback font should none of the others be available.

See the `index.css` for config variables and `reset.css` for the CSS.

###	post_text_font

The font used for the normal text on your site. This font is set on the CSS for the `body {}`.

``` toml
post_text_font = "Bitter, Source Sans Pro"
```

Produces this CSS code:

``` css
#post-article {
  font-family: Bitter, Source Sans Pro, sans-serif;
}
```

This will use the Bitter, then the Source Sans Pro font for text. Note that whatever you put here will have sans-serif added as the final fallback font should none of the others be available.

See the `index.css` for config variables and `reset.css` for the CSS.

## Configuration - [Params.Background]

This section allows your site to have a background image. If you do not tile the image, it gets anchored in the top-left corner of the window

### src

Url of the image displayed as the site background.

``` toml
src = "/images/background.jpg"
```

### fit_width

Shrink the image to fit the width of the window.

``` toml
fit_width = true
```

### tile

Tile the image across the window.

``` toml
tile = false
```
## Configuration - [Params.Color]

Change any or all of the page colors.

### page_background_color

Fairly self-explanatory - color of the *page* background. This is different from the window background color as the page sits within the window.

```toml
    page_background_color = "#000000"
```

### main_background_color

Background color of the window (site container), where the background image sits. Note that the *page* sits inside this window, hence why you can have two different colors.

``` toml
main_background_color = "#050505"
```

### alt_background_color

Alternate background of site container, used on inactive buttons, alternating table rows, and `<code>` and `<pre>` elements (code fields).

``` toml
alt_background_color = "#252525"
```

### body
_text

The text color to correspond with main_background_color.

``` toml
body_text = "#e2e2e2"
```

### alt_body_text

The text color to correspond with alt_background_color.

``` toml
    alt_body_text = "#e2e2e2"
```

### accent_color

Accent color, used for active buttons and links.

``` toml
accent_color = "#2c8cef"
```

### header_text

Color of the site header text.

``` toml
    header_text = "#e2e2e2"
```

### Sidebar widgets [Params.widgets]

### recent_articles

Show the ten most recent posts under /post/.

``` toml
recent_articles = true
```

### categories

Show the top 5 categories in use on your site

``` toml
categories = true
```

### tags

Show the tags used on your site, ordered by most common

```toml
tags = true
```

### tags_counter

Include a parenthetical count of how often a tag has been used.

``` toml
tags_counter = false
```

### twitter_feed

This adds your twitter timeline to the sidebar and shows the last tweets from your feed. For the timeline to appear you also need to have set [twitter](#twitter) under [Params.Social][#social-icons---paramssocial]. The number of tweets to be shown has to be > 0.

``` 
# Show the last 3 tweets from my twitter feed
twitter_feed = 3
```

### patreon

Show a Patreon banner in the sidebar linking to the URL specified here.
Note: Since this is originally a dark theme, the banner used is white. Eventually I will get around to making it configurable

``` toml
patreon = "https://patreon.com/shadow53"
```

### Social Icons - [Params.Social]

BluestNight supports linking to a number of popular social sites from icons in the site footer. If the service normally uses usernames prefixed with an "@", your username should be entered *without* one.

``` toml
[Params.Social]
	deviantart = "username"
	facebook = "userid"
	github = "pauby"
	googleplus = "+Joe-Smith"
	instagram = "username"
	linkedin = "paulbroadwith"
	pinterest = "username"
	reddit = "pauby"
	spotify = "username"
	tumblr = "username"
	twitter = "pauby"
	steam = "userid"
```

### deviantart

Your deviantart username.

``` toml
deviantart = "username"
```

### facebook

Your Facebook user id is what comes after "https://facebook.com/" on your public profile page.

``` toml
facebook = "userid"
```

### github

Your Github user name.

``` toml
github = "username"
```

### googleplus

Your GooglePlus username.

``` toml
googleplus = "+name-surname"
```

### instagram

Your instagram username.

``` toml
instagram = "username"
```

### linkedin

Your LinkedIn name. This is the part that appears at the end of your profile page URL and is generally <FIRSTNAMELASTNAME> in lowercase.

``` toml
linkedin = "userid"
```

### pinterest

Your username is whatever follows "https://pinterest.com/" on your profile page

``` toml
pinterest = "username"
```

### reddit

Your Reddit username.

``` toml
reddit = "pauby"
```

### spotify

Your Spotify username.

``` toml
spotify = "pauby"
```

### tumblr

Your tumblr username.

``` toml
tumblr = "pauby"
```

### twitter

Your Twitter username (without the @).

``` toml
twitter = "pauby"
```

### steam

Your Steam userid.

```
steam = "userid"
```

### Shortcodes

#### Member Boxes

The memberbox is equivalent to the authorbox, except that memberboxes can be displayed anywhere in a piece of content using the `{{< member "Member Name" >}}` shortcode. Replace `Member Name` with the name of the member as found in the `Name` attribute of the data file in `/data/members/`. See [Authorbox](#authorbox) for more on the data file.

##### Example:

```markdown
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque convallis sollicitudin arcu sed volutpat. Suspendisse ante erat, elementum eget orci a, consectetur condimentum est. Sed leo ipsum, laoreet eu rhoncus id, posuere ut sem. Pellentesque blandit, tortor sit amet lobortis tristique, sem felis pellentesque orci, vel interdum lacus magna et est. In fringilla facilisis ultrices. Maecenas at bibendum tellus. Vivamus imperdiet volutpat lacus, a tempor enim rutrum at.

{{< member "Joe Smith" >}}

Sed tristique ex eros. Donec vestibulum nunc sed mattis efficitur. Mauris mollis libero quis tellus interdum, id venenatis dolor gravida. Praesent dignissim tempor blandit. Duis ut nisi eget arcu molestie dapibus. Cras viverra magna id tincidunt ultrices. Nam id cursus diam, in ultricies sem. Ut convallis eget metus non feugiat. Integer elementum consequat risus vitae lobortis. Curabitur dapibus, lectus nec vulputate laoreet, leo elit gravida odio, ac dapibus nisl ex vel justo. Maecenas ornare lobortis ante nec blandit.
```

#### Handwriting styles

The theme comes with a handful of 100% free handwriting fonts from [Font Squirrel](https://www.fontsquirrel.com/). You can choose between them using the `{{% handwriting %}}` shortcode. These are the currently available fonts:

- `"allura"`
- `"calligraffiti"`
- `"dancing-script"`
- `"daniel"`
- `"euphoria-script"`
- `"journal"`
- `"kingthings-wrote"`
- `"note-this"`
- `"vag-handwritten"`

##### Example:

```
{{% handwriting "calligraffiti" %}}
This is some text that will render using the "calligraffiti" font.
{{% /handwriting %}}
```

### Output - [outputs]

This requires also adding `CSS` as an output type for the home page.

```toml
[outputs]
    home = ["HTML", "CSS"]
```
