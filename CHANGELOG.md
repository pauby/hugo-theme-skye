# Theme For Hugo - Skye

Changes only recorded from v0.50

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
