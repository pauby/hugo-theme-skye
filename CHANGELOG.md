# Theme For Hugo - Skye

Changes only recorded from v0.50

# 0.55 

* Tags list in the sidebar had a fixed font size of 12px. This has been removed to allow CSS styling;
* Improve the look of the date and estimated reading metadata in the header by replacing missing icons with fontawesome ones and styling with CSS;
* Centred post title and metadata in the list template;
* Corrected a typo that stopped the calendar icon on the date being fixed width;
* Removed inline styling from the post banner page and replaced with CSS code;
* Fixed issue where tags would not centre correctly at the bottom of the post and the tag icon was missing;

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
