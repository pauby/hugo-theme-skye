# Theme For Hugo - Skye 

(See [changelog](/CHANGELOG.md) for latest version and changes)

A dark theme with blue accents for Hugo. Provides multiple configuration options and overrides.

## Features

You can find more details on certain features by scrolling down past this list

- Disqus commenting (fixed for testing with localhost and can be disabled by content)
- Big cover image (optional)
- Custom cover by content (optional)
- Google Analytics (optional and disabled when running on localhost)
- Font Awesome support (local CSS and using embed code)
- [Site header with tagline](#site-headertagline)
- Responsive design using [CSS flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes)
- [Configurable color scheme](#custom-colors)
- [Custom site wallpaper](#custom-wallpaper)
- Custom CSS that cleans the page up for printing *only* the page content (try visiting one of the example pages and viewing print preview)
- [Custom shortcodes](#shortcodes) that I find useful
- [Multiple sidebar widgets](#sidebar-widgets), including:
  - Categories list
  - Recent posts list
  - Post tags list (sorted by most common)
  - Twitter timeline
- Optional [authorbox](#authorbox) on post pages
- `_index.md` support for all list pages, including custom content and hiding the list
- Pagination
- [Custom section landing pages](#custom-section-landing-pages)
- Dynamic site menu that works on desktop and mobile alike - supports seemingly infinite nesting (might look bad on mobile, though)
- Comments can be enabled/disabled on a per-page basis as well as in the site config
- Dynamic taxonomy pages that look good on all screen sizes
- Social icons in the page footer
- Custom "Error 404" page
- Custom robots.txt that prevents taxonomy pages from being indexed (e.g. /tags/my_tag)
- Check out the [TODO list](https://github.com/Shadow53/BluestNight)

## Template `config.toml`

``` toml
languageCode = "en-us"
title = "My Website"
baseurl = "https://example.com/"
theme = "BluestNight"
enableRobotsTXT = true # Use custom robots.txt
PygmentsCodeFences = true
PygmentsStyle = "monokai" # Use "igor" for light backgrounds

[Params]
    tagline = "An example tagline for my Hugo site" # Subtitle of your site
    description = "Here is a description of my site that will appear in search engine results - W00t!" # Description of your site
    cover = "/images/cover.jpg"
    authorbox = true
    authorboxTop = true
    author = "Some Guy" # Name must exist in an entry in /data/members
    postNavigation = false
    RSSLink = "http://feeds.feedburner.com/yoursite.xml"
    rssDisableSummary = true

    cssAddHead = ["/css/powershellconsole.css" ]
    jsAddHead = [""]	# Javascript URL's to place inside <script src=> tags in the header
    jsAddFoot = [""] 	# Javascript URL's to place inside <script src=> tags in the footer

    fontawesome = true
    fontawesomeCdnEmbedcode = "1234567890"

[Params.Footer]
    copyright = "&copy; pauby.com 2017. Powered by Hugo."

# Custom background for the site
[Params.BackgroundImage]
    src = "/path/to/background.png"
    fit_width = true
    tile = false

[Params.fonts]

    loadGoogleFont = [ "Lato", "Libre Franklin" ] 

    main = "Lato"
    postHeader = "Libre Franklin, Arial"
    postText = "Libre Franklin, Arial"
    code = "Courier New"

# These are the default colors used in the theme
# Change them to whatever you'd like
[Params.Color]
    backgroundPage = "#000000"
    backgroundWindow = "#050505"
    backgroundAlt = "#252525"
    textDefault = "#e2e2e2"
    textAlt = "#e2e2e2"
    accent = "#2c8cef"
    textHeader = "#e2e2e2"

[Params.Social]
    github = "username" # Your GitHub username
    facebook = "your_fb_id" # Your Facebook ID - the part that comes after https://facebook.com/ on your profile page

[Params.Widgets]
    articleRecent = true # Enable "Recent arcticles" widget
    categories = true # Enable "Categories" widget
    tags = true # Enable "Tags" widget
    tagCount = true # Enable tag count on tag widgets
    upcoming_events = false
    my_twitterFeed = true

# This is required for CSS to work
[outputs]
    home = ["HTML", "CSS"]

```

See [Configuration](/CONFIGURATION.md) for a detailed explanation of each option.

## Displaying Code On Your Site

See the [Hugo documentation](https://gohugo.io/extras/highlighting/) on this.

### Pygments

If you are going to use [Pygments](http://pygments.org/) to highlight your code then see below for my suggested configuration within the root section of your `config.toml`:


``` toml
PygmentsUseClasses = false
PygmentsCodeFences = true
PygmentsStyle = "monokai"
```

If you are happy with the default appearance of the the Pygment Styles then use `PygmentsStyle` variable to your preferred [style](http://pygments.org/docs/styles/). Otherwise remove the variable and include your preferred CSS in the page `<head>`. See [cssAddHead](#/CONFIGURATION.md#cssAddHead).

``` toml
PygmentsUseClasses = true
PygmentsCodeFences = true
cssAddHead = ["/css/myHighlighter.css"]
```
