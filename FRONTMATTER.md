# Hugo Theme - Skye

## Section Configuration

### Custom Section Landing Pages

Rather than have Hugo generate a page of nothing but the content under a section,
maybe you'd like to introduce the content with a paragraph or two first. If you
place a `_index.md` file with the desired content in the root of the section folder,
BluestNight will place that text before the content list.

Bonus! If you want to hide the list and show only your custom content, just add
a line setting `hide_list` to `true` in the front matter of `_index.md`.
