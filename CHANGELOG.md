# Theme For Hugo - Skye

Changes only recorded from v0.50

# 0.61.3

* Post banner image is no longer the full width of the browser window but is not centred across the page.

# 0.61.2

* Changed the internal names of variables in index.css;
* Fixed an issue where there would be a large gap between the bottom of an ordered list and the next text;
* Fixed an issue where the url in the tag and category widget was malformed;

# 0.61.1

* Removed the localhost checking within the Google Analytics Javascript code and replaced with with the new Hugo .Site.IsServer;

# 0.61.0

* Updated documentation for listHide, eventUpcoming and readingtimeHide;
* Removed page banner for smaller screens;
* Adjusted the main container size for large and medium screens;
* Changed the post headers and metadata to be left aligned by default when displaying the post and in a list;
* Fixed issue with events widget not referencing correct eventUpcoming configuration variable;
* Removed patreon widget and CSS;
* Added readingtimeHide configuration variable that will hide the 'Estimated reading time' metadata for a post. This can be specified in the config file to be applied site wide. It can also be specified in the frontmatter of a post which will override the site wide configuration;
* Post tags now display in the post metadata and have been removed from the bottom of a post;
* Fixed an issue where there would be a large gap between the bottom of a list and the next text;
* Made <!doctype> uppercase;
# 0.60.1

* Replaced configuration name `hide_list` with `listHide`;
# 0.60

* Stopped processing of the post title and description for opengraph, twitter card and RSS feed XML;

* Replaced configuration names in frontmatter:
  | Before | After |
  |--------|-------|
  | thumbnail_css_class | thumbnailCssClass |
  | thumbnail_hide_list | thumbnailHideList |
  | thumbnail_caption | thumbnailCaption |
  | authorbox_top | authorboxTop |
  | hide_authorbox | authorboxHide |
  | short_description | descriptionShort |
  | disable_comments |commentsDisable |

* Replaced configuration names in site config:
  | Before | After |
  | ------ | ----- |
  | hide_rss | rssHide |
  | post_navigation | postNavigation |
  | rss_disable_summary | rssDisableSummary |
  | custom_css | cssAddHead |
  | custom_js_head | jsAddHead |
  | custom_js_foot | jsAddFoot |
  | fontawesome_cdn_embedcode | fontawesomeCdnEmbedcode |
  | Params.Fonts.code_font | Params.Fonts.code |
  | Params.Fonts.default_font | Params.Fonts.default |
  | Params.Fonts.googlefonts | Params.Fonts.loadGoogleFont |
  | Params.Fonts.post_header_font | Params.Fonts.postHeader |
  | Params.Fonts.post_text_font | Params.Fonts.postText |
  | Params.Background.src | Params.BackgroundImage.url |
  | Params.Background.fit_width | Params.BackgroundImage.fitWidth |
  | Params.Background.tile | Params.BackgroundImage.tile |
  | Params.Color.page_background_color | Params.Color.backgroundPage |
  | Params.Color.main_background_color | Params.Color.backgroundWindow |
  | Params.Color.alt_background_color | Params.Color.backgroundAlt |
  | Params.Color.body_text | Params.Color.textDefault |
  | Params.Color.alt_body_text | Params.Color.textAlt |
  | Params.Color.accent_color | Params.Color.accent |
  | Params.Color.header_text | Params.Color.textHeader |
  | Params.Widgets.recent_articles | Params.Widgets.articleRecent |
  | Params.Widgets.tags_counter | Params.Widgets.tagCount |
  | Params.Widgets.twitter_feed | Params.Widgets.twitterFeed |
  | Params.Widgets.upcoming_events | Params.Widgets.eventUpcoming |

* Moved Params.Footer.copyright into main Params sections and removed Params.Footer section;

* Removed Hashover commenting system;

# 0.59.1

* In v0.53 `sharing_tweet` was renamed `short_description` however this was not being used in the `twitter:description` metadata. Fixed this bug.

# 0.59
* Added support for thumbnail_hide_list - hides the thumbnail from displaying on list pages;
* Added website to authorbox;
* Added option to have the authorbox at the top of the article or the bottom. Use `authorbox_top = true` in the post frontmatter to have it apply to that post or add it to the site config file to have it apply everywhere;  

# 0.58
* Removed frontmatter `thumbnail_offset` and replaced with `thumbnail_css_class` to allow you to apply individual CSS to page banners. If this is not set then the default `post-banner` CSS class will be applied;
* Header image caption is now on image itself - bottom right;
* Added categories to RSS.xml;
* Some fonts dont; appear in bold when using `<bold>` or `<strong>` - added CSS to give these HTML tags the correct weight;

# 0.57
* Added new shortcode - mva - allows Microsoft Virtual Academy videos to be embedded. Video will expand to the size of the current div it is in;
* Added ability to adjust the offset of the background image that is shown on a page;
* Fixed footer colours and events layout spacing;
* Fixed tags url which had spaces being added and caused 404 errors;

# 0.56

* Amended events widget to: display event until end time expires; add a url for more information to the event title; styled event with boredrs around date;
* Added caption for list pages with thumbnail banner;
* Fixed issue with header not loading Google fonts;

# 0.55 

* Tags list in the sidebar had a fixed font size of 12px. This has been removed to allow CSS styling;
* Improve the look of the date and estimated reading metadata in the header by replacing missing icons with fontawesome ones and styling with CSS;
* Centred post title and metadata in the list template;
* Corrected a typo that stopped the calendar icon on the date being fixed width;
* Removed inline styling from the post banner page and replaced with CSS code;
* Fixed issue where tags would not centre correctly at the bottom of the post and the tag icon was missing;
* Changed the list page thumbnail to be a maximum width of 200px rather than focus on height size;
* Added [Params.fonts] section and added default_font which applies to all text on the site, post_header_font which styles post headers and post_text_font which styles the text of the post text;

# 0.54

* Moved the RSS template to a searched directory (#15);
* Added hide_rss frontmatter variable to stop pages being added to the RSS feed (#16);
* Increased page width to match browser, increased size definition of a large screen to 1366px and adjusted column percentages for large screens;
* Boxed the post sharing icons, formatted them so that if they wrap due to screen size they maintain their margins and added instructions;
* Centred the post tags and pushed them to be at the bottom of the post;
* Removed bold from CSS header (h1 etc.) and resized them;
* Moved the image banner to be above the content and sidebar; 
* Added hide_rss frontmatter variable to stop pages being added to the RSS feed (#16)
* Changed the config variable 'my_twitter_feed' to 'twitter_feed' and allows you to provide a number for the tweets to be shown (#17)

# 0.53

* Created [[metadata]] front matter variable to allow metadata to be inserted into the page;
* Renamed the front matter configuration 'sharing_tweet' to 'short_description'; 
* Removed hosted font images and used fontawesome
* When no menus were configured the site did not render - added a check for this and skip rendering menus if none existed (#10);
* Added Meetup social icon (#11);
* Fixed footer links colour;
* Fixed colours of social icons within the authors box - colour of icons is now the body_text as defind in the config file (#12);
* Added meetup icon to the authorbox. Member just has to add 'meetup = <meetup name>' in their member data file for it to be added (#13);

# 0.52

* Added tags to list item metadata and tidied up font sizes around the metadata
* Amended the default post front matter to replace the mistyped JSON with TOML

# 0.51

* Added twitter timeline widget
* Added custom footer copyright
* Replaced widget icons with Fontawesome equivalents
* Fixed post archetype typo in front matter
