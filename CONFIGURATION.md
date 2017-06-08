# Hugo Theme - Skye

## Configuration - [Params]

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

## Configuration - [Params.Background]

This section allows your site to have a background image. If you do not tile the image, it gets anchored in the top-left corner of the window

```toml
[Params.background]
    # Path or link to the image
    src = "/images/background.jpg"
    # Shrink image to fit the full width in the window?
    fit_width = true
    # Tile the image?
    tile = false
```

## Configuration - [Params.Color]

Change any or all of the page colors:

```toml
[Params.color]
    # Background of page behind site container, where background image goes
    page_background_color = "#000000"
    # Background of site container
    main_background_color = "#050505"
    # Alternate background of site container, used on inactive buttons,
    # alternatings table rows, and <code> and <pre> elements (code fields)
    alt_background_color = "#252525"
    # The text color to correspond with main_background_color
    body_text = "#e2e2e2"
    # The text color to correspond with alt_background_color
    alt_body_text = "#e2e2e2"
    # Accent color, used for active buttons, links, and the site header
    accent_color = "#2c8cef"
    # A text color to correspond with using accent_color as a background color
    header_text = "#e2e2e2"
```

This requires also adding `CSS` as an output type for the home page, e.g.:

```toml
[outputs]
    home = ["HTML", "CSS"]
```

### Sidebar widgets

```toml
[Params.widgets]
    # Show the ten most recent posts under /post/
    recent_articles = true
    # Show the top 5 categories in use on your site
    categories = true
    # Show the tags used on your site, ordered by most common
    tags = true
    # Include a parenthetical count of how often a tag has been used
    tags_counter = false
    # Show a Patreon banner in the sidebar linking to the URL below
    # Note: Since this is originally a dark theme, the banner used is white.
    # Eventually I will get around to making it configurable
    patreon = "https://patreon.com/shadow53"
```



### Custom Section Landing Pages

Rather than have Hugo generate a page of nothing but the content under a section,
maybe you'd like to introduce the content with a paragraph or two first. If you
place a `_index.md` file with the desired content in the root of the section folder,
BluestNight will place that text before the content list.

Bonus! If you want to hide the list and show only your custom content, just add
a line setting `hide_list` to `true` in the front matter of `_index.md`.

### Social Icons

BluestNight supports linking to a number of popular social sites from icons in
the site footer. If the service normally uses usernames prefixed with an "@",
your username should be entered *without* one. Currently supported are:

``` toml
deviantart = "username"
# Your Facebook user id is what comes after "https://facebook.com/" on your public profile page
facebook = "userid"
github = "userid"
googleplus = "+name-surname"
instagram = "username"
linkedin = "userid"
# Your username is whatever follows "https://pinterest.com/" on your profile page
pinterest = "username"
reddit = "userid"
spotify = "username"
tumblr = "username"
twitter = "userid"
steam = "userid"
```

### Shortcodes

#### Member Boxes

The memberbox is equivalent to the authorbox, except that memberboxes can be
displayed anywhere in a piece of content using the `{{< member "Member Name" >}}`
shortcode. Replace `Member Name` with the name of the member as found in the
`Name` attribute of the data file in `/data/members/`. See [Authorbox](#authorbox)
for more on the data file.

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
