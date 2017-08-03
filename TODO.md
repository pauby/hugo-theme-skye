# Hugo Theme - Skye

## Documentation

- [ ] Update docs

## Layouts

- [ ] Update / create / amend / assess SEO;
- [X] Set [taxonomies]categories = "" and have the templates still work;
- [X] if googleFonts (in config file) contains '+' then it is renders using the '%2b' html code. Raised [Hugo issue](https://github.com/spf13/hugo/issues/3588) for this and need to update this task accordingly.

## Widgets

- [ ] Fix authorbox social-icons colour
- [ ] Remove / replace patreon banner with freetext box
- [ ] Add explanation for upcoming_events (also see [this](https://gohugo.io/templates/introduction/))

## Misc

- [ ] Get the site working HTTP or HTTPS
- [ ] Add site search using https://lunrjs.com/
- [ ] Add default copyright notice if one is not specified

## Content

- [ ] Add .Next, .NextInSection and .Prev, .PrevInSection (see [this](https://gohugo.io/variables/page/))
- [ ] Add Categories option for list page

This is the TODO list from the forked [BluestNight](https://gitlab.com/Shadow53/BluestNight) project. Items will be gradually migrated across to the project list.

## Widgets

- [ ] Add a blogroll / favorite links menu widget in the sidebar - .fi-link icon?
- [ ] Add search widget to sidebar - .fi-magnifying-glass icon
- [ ] Donate with Paypal widget? - .fi-paypal icon
- [x] Fix menu visibility issues
   - Menu is not visible on large screen if previously hidden (JS fix)
   - Menu is not visible on small screen if above happens (JS fix)
   - [x] Submenu does not expand after leaving small screen size (JS fix)
- [ ] [Google Analytics](https://gohugo.io/extras/analytics/)
- [X] Custom ordering of widgets in the sidebar - the easiest way to do this was a custom sidebar.html in the site (not theme) and customise it for the pages you want. I did experiment adding this to the front matter but it just got too complicated and then I had the issue with list pages and how they would be configured;

## Archetypes

## Posts

- [x] Add customizable and privacy-friendly comment system
- [x] Allow optionally overriding site page navigation setting
   - [ ] Optionally show only the next or previous nav, even if Hugo says the other exists
- [x] Optionally include a Table of Contents for the page

## Templates

- [ ] Implement [blocks](https://gohugo.io/templates/blocks/)
- [x] Generate [pages for tags/categories](https://gohugo.io/templates/terms/) (also taxonomy lists on [this page](https://gohugo.io/templates/list/) and [this one](https://gohugo.io/taxonomies/displaying))
- ~~[ ] Custom [home page](https://gohugo.io/templates/homepage/)?~~
  - People should be able to use `_index.md` to modify their home page, even hiding the list
- [x] Templates for list pages containing `{{ .Content }}` for custom content ([Docs](https://gohugo.io/content/using-index-md/))

## Other
- [x] Reduce dependencies on JavaScript as much as possible
  - [x] Bonus: remove all dependencies on JavaScript so the theme is only HTML and CSS
     - [x] [CSS3 Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations) to show/hide menu
       - This is made harder by having Foundation as the CSS framework library because it determines how to organize the site based on screen size. I'd have to have a screen size rule matching the small screen detection for hiding the menu and showing the toggle, and another rule for doing the opposite on larger screens.
       - Perhaps I should also remove the dependency on Foundation, since it includes a bunch of styling I don't need anyways?
- [ ] Card-esque items in post list?
- [ ] Implement microdata based on [Schema.org](https://schema.org/docs/gs.html)
- [x] Use CSS3 [@page](https://developer.mozilla.org/en-US/docs/Web/CSS/@page) to modify the look for printing
- [ ] Use CSS3 [@viewport](https://developer.mozilla.org/en-US/docs/Web/CSS/@viewport) for small screens (Does Foundation already do this?)
- [ ] Use CSS3 [@supports](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports) when necessary, e.g. for text select color
