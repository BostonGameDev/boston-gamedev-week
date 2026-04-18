# BOSTON GAMEDEV WEEK

[![Deploy Jekyll with GitHub Pages dependencies preinstalled](https://github.com/YWainczak/bostonIndies/actions/workflows/jekyll-gh-pages.yml/badge.svg)](https://github.com/YWainczak/bostonIndies/actions/workflows/jekyll-gh-pages.yml)

The official Boston Gamedev Week website.

Written using HTML, SCSS, and Liquid. Compiled by Github Page's version of Jekyll.

Google Font Icon settings
Weight: 400
Grade: 0
Optical Size: 48px
Style:
 - Material Symbols
 - Rounded

To build locally, use `bundle exec jekyll serve`.

## Resources

The website uses numerous resource types to create things like the schedule. Resources have custom front-matter that should be filled out in order to make the schedule look correct.

### Events

Events are the lifeblood of the system. In the `_events` folder you will find a folder for each year with markdown files for each event. 

#### Front Matter
|Property|Value|Notes|
|---|---|---|
|layout|`event`|HTML template. `event` should be the only value.|
|title|"EVENT NAME"|This should be short for the front page.|
|date|YYYY-MM-DD hh:mm:ss America/New_York|Make this the same as the start_date. We should try to take this out if possible.|
|start_date|YYYY-MM-DD hh:mm:ss America/New_York|When the event starts.|
|end_date|YYYY-MM-DD hh:mm:ss America/New_York|When the event ends. This can span multiple days. I think as a hack we use the date part and assume it starts at the same time every day if it spans multiple days.|
|location|`location-name`|If this matches a file with the proper "index" in the _location folder, it will use the info from that location on this page for things like address, directions, code of conduct.|
|banner|"YachtClub.png"|Image to use from `assets/resources/banners`.|
|ticket_type|<optional>`pax` or `ticketed`| Display an icon on the front-page showing it requires a PAX badge or you must pay or RSVP elsewhere. Leave out completely for free events like Demo Night.|

#### Content
After the front matter, should just describe anything you need to about the event. Provide links to any ticketing required. Describe who should go. Whatever!

As long as you filled out the location and provided a valid location resource from the `_location` folder, lots of extra content will show up here. Direction, address, parking, code of conduct.

### Locations

Locations are referenced by `index` and provide all the information that you would normally repeat for each event. For example, you don't want to re-type parking info all the time! 

#### Front Matter

|Property|Value|Description|
|---|---|---|
|index|"little-wolf"|The id that will be used by an `_event`|
|title|"Little Wolf"|The name of the place!|
|maps|"Little Wolf Coffee"|How this can be searched on Google Maps to get directions.|
|address|"51 Sleeper St, Boston, MA 02210"|<optional> A specific address override, if Google Maps is failing.|

#### Content

Here it is helpful to put any information specific to the venue that should show up on all pages. Since it is a markdown file, you can style it. Best practice: Headers should be no higher than H3 since this will be contained in other pages. 

For example, at MIT we have:

```
MIT Open Space is an outdoor venue located just outside the MIT Museum.

### Parking
Feel free to visit the [Official MIT Open Space transportation & parking webpage](https://www.openspace.mit.edu/visit) for information on parking.

There is parking at the Hayward lot (directly under the Open Space) but we recommend taking public transit. MIT is a short walk from the Kendall Square Red Line station.

### Harassment Policy

By attending, you agree to adhere to the [MIT Game Lab Harassment Policy](http://gamelab.mit.edu/harassment-policy/).

If you experience any harassment or other disrespectful behavior, please report it to Boston Indies Staff, any of our socials through direct messaging, or speak with any MIT staff at the event.
```

## Deploying Your Changes

"To make things live, once you've got everything created, you use rvm. (Ruby Version Manager.) I'm on Ruby 3.3.7. You use bundle exec jekyll serve to spin up locally. That and the command bundle exec jekyll server create the site in a _site folder. So, because I had to write a piece of code to check if dates are in a certain range, you have to manually push the site. After you commit to main and push that (not including the _site folder), you have to switch to the gh-pages branch. Then I just cp -r _site/* . and git add . and then git commit -m "some message" and then git push origin gh-pages." - Chad
