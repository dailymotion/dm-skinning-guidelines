Dailymotion skinning guidelines - Custom campaign specifications
==============================
![Dailymotion logo](http://www.underconsideration.com/brandnew/archives/dailymotion_logo_detail.png)

Element insertion
--------------------------
- Element insertion above the header is forbidden
- New elements ids and classes should be prefixed 'dm-ad' to avoid conflicts.
- For top banner and skinning, please refer to [the specific section](#top-banner-formatting).

HTML Formatting
----------------------------
- Code should be submitted without ```html```, ```title```, ```head``` or ```body``` tags
- All html attributes must be properly double-quoted
- All tags should be correctly nested and closed (except for self-closing tags)

CSS Formatting
------------------
Additionnal css style **must not change** these following rules on any element on the page:
- ```z-index```
- ```position```

Skin formatting
----------------------
**Apply background only on ```div#wrapper```.** 

This will allow the background to be properly moved with the navigation menu.
Custom scripts should follow these specifications in order to maintain the site coherence. For new formats, please check feasability with the technical team.

```javascript
$('#wrapper').css({
 background: 'url(http://i.imgur.com/KDSGJ1j.png)'
});
```
Create ```div``` to handle click redirection:

- The ```div``` should be 100% width and 100% height
- It should be the first child of the ```div#wrapper```
- You should add a callback on the click event to handle the redirection

```javascript
var clicker = $('<div />);
// configure and position the div
clicker.css(
{
  position: 'absolute',
  width: '100%',
  height: '100%',
  top: 0,
  left: 0,
  zIndex: 0,
  cursor: 'pointer'
});
// put the div in div#wrapper as the first child
$('#wrapper').prepend(clicker);
// add a callback on the click event
clicker.on('click', yourCallback);
```

Top banner formatting
---------------------------
**Top banner elements should be included in the ```div#top_banner```.**

Top banner elements include:
- simple banner
- masthead
- transparent flash
- pushdown

Campaign testing
------------------------
**Each item of the list should be tested before ANY CAMPAIGN RELEASE**

- [ ] check navigation panel
- [ ] login and check user menu
- [ ] check header display
- [ ] check footer display
- [ ] check if the site fit in the window (no horizontal scroll)
- [ ] check the campaign on different viewports
