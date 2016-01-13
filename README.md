Learn GeoJSON 
=============

Remember last maptime, when we made a leaflet map and we manually looked up and entered coordinates for our points? We'll here's a project to learn about GeoJSON, a data format for geographic information. This tutorial also uses git, GitHub, and geojson.io to build a collaborative data set.

The following sections are intended for absolute beginners. If you're an intermediate or advanced user, great! Feel free to skip ahead to the project instructions.

## Background Knowledge

### What is GeoJSON?

[GeoJSON](http://geojson.org/geojson-spec.html) is an open and popular geographic data format commonly used in web applications. It is an extension of a format called [JSON](http://json.org), which stands for *JavaScript Object Notation*. GeoJSON extends JSON by adding a section called "geometry" such that you can define coordinates for the particular object (point, line, polygon, multi-polygon, etc). A point in a GeoJSON file might look like this:

    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [
          -122.65335738658904,
          45.512083676585156
        ]
      },
      "properties": {
        "name": "Hungry Heart Cupcakes",
        "address": "1212 SE Hawthorne Boulevard",
        "website": "http://www.hungryheartcupcakes.com",
        "gluten free": "no"
      }
    }
    
GeoJSON files have to have both a `"geometry"` section and a `"properties"` section. The `"geometry"` section houses the geographic information of the feature (its location and type) and the `"properties"` section houses all of the descriptive information about the feature (like fields in an attribute table).

### What are git and GitHub?

[Git](http://git-scm.org) is a tool that allows multiple people to work on the same files at the same time without overwriting each other’s changes. This general concept is called *version control*, and git is a *version control system*. There are several other version control systems out there, but git is popular because it does its job more efficiently than many (if not all) of the others.

In order for multiple people to work on a project, the data has to live in a place where multiple people can access it. [GitHub](http://github.com) is one of those places: the site houses thousands and thousands of projects, in individual workspaces called *repositories*, or *repos*, that multiple people can access, copy, edit, and update using the tools available via git. (Guess what: You're inside of a repo right now!) These repositories also have a tracking element; when someone makes a change to a project, or a *commit*, information is stored about the user, the time, the exact changes that were made (all the way down to the individual line inside the file!), and a unique ID that allows the project owner to restore back to that particular moment.

### Why are we using GitHub and GeoJSON?

[Tom MacWright](http://www.mapbox.com/about/team/#tom-macwright) over at [MapBox](http://mapbox.com) has built an amazing, browser-based tool for editing GeoJSON files called [geojson.io](http://geojson.io). Using some of the great tools available via [MapBox.js](http://www.mapbox.com/mapbox.js/api/v1.3.1/), [Leaflet](http://leafletjs.com), and some [internal GitHub functionality](https://github.com/blog/1528-there-s-a-map-for-that), geojson.io allows users to easily edit and create geographic data in the browser.

### Awesome! How do I contribute?

There are a few things that are required for you to contribute to this dataset. First of all, you need to make yourself a GitHub account, if you don't have one already. It's free and easy to set up, and should take less than five minutes.

I would also advise downloading [git](http://git-scm.org). Click the link and download the recommended version.

Beyond that, there are two main ways to contribute to this dataset: one is to **edit existing files** by adding points to them. The other is to **create a new file**, add it to the repository, and make them available for editing. MORE MAPS! There are step-by-step instructions for doing each of these, below.

## Project Instructions

These are the files that are currently in the repository and can be edited:

  - [nolaplaces.geojson](geojson/nolaplaces.geojson): A dummy dataset for practice.
  - [kingcakeries.geojson](geojson/kingcakeries.geojson): A map of places to get sweet, delicious king cake! 
  - and.... any other maps we wanna make! 

1. If you haven't done so yet, get yourself a [GitHub](http://github.com) account and download [git](http://git-scm.org). (These instructions don't use git on the command line, but many of these principles can be used and mirrored with git in the command line.)

2. Once you're all logged in to your GitHub account, navigate over to the [maptimenola-geojson](http://github.com/emilyashley/maptimenola-geojson) repo and press the button at the top that says Fork. *Forking* a repo makes a copy of it that is all yours. Head on over to github.com/[yourusername]/maptimenola-geojson. This is your copy of the repo!


3. In *your* copy, click through to the file you want to edit. You should see a nice little map rendering the points in the dataset. Just for fun, click on one of the points. A popup appears with attribute information for the point! Neat, huh?

4. Head on over to [geojson.io](http://geojson.io). Click 'login' on the top right corner and authorize. Now click GitHub on the top, navigate through to the GeoJSON file you want to edit, and press Open. The GeoJSON file is now open and editable in geojson.io.

5. Add a point by selecting the point tool and clicking on the map to place the marker.

6. Notice there's a section labeled "table." This is where you can easily add and edit information for your point. Next to it, there's a little button that says "</> JSON" on it. Go ahead and click on that.

7. This is GeoJSON! Take a look at the last point in the list. It's the one you just created! Each of your attributes is in the "properties" section, and there are coordinates for where you placed the point housed in the "geometry" section. You can edit the properties and geometry directly in the GeoJSON view. If you edit the GeoJSON directly and accidentally break something, use [GeoJSONLint](http://geojsonlint.com/) to find errors. What you're doing is adding some lines of code to a .geojson file! This will be important later.

8. Add as many more points as you want. Seriously. Go to town.

9. When you're done adding points, click Save on the top bar. A small box appears asking for a "Commit message." Type in a short description of the points you added and press Commit. This message will be saved on github along with the changes to the geoJSON file.

10. Once you've done that, a little box pops up in the same area that says, "Changes committed to GitHub:" followed by a series of numbers and letters. Click on the numbers/letters.

11. This is a list of all of the commits for the repository. This list will include not only the commits you've made, but also all of the commits that were made to the dataset before you forked it.

12. Click on the number/letter combination for your most recent commit. This is why git is so neat: GitHub is showing you the exact lines that were changed in the GeoJSON file with a nice little comparison between the line you changed before you committed, and the line after.

13. Click back out to your version of the repo. In the right column, click Pull Requests.

14. A [pull request](https://help.github.com/articles/using-pull-requests) allows the user of a forked repo to push her changes back up to the original repo. For collaborating on datasets, it's a pretty cool tool! Click the green button that says "New pull request" at the top.

15. A screen pops up showing any commits you've made to the repository since you forked it and any changes you may have made to any files in the repository. This is to show you what you're asking the owner of the repo to change and/or include. If it all looks good, click the link at the top that says "Click to create a pull request for this comparison."

16. Give your request a title (something along the lines of "Adding Jessica's places!") and a short description of what you added. When you're ready, click the green "Send pull request" button.

17. Once the repo owner has approved your pull request, GitHub will tell you that your request was merged. Then your changes will be reflected in the parent dataset!

18. Click back over to the repo you forked from, click through to the geojson file you edited, and take a look. Your points will have been added to the original dataset. Congratulations! 


We're off to a good start! There's a lot more to learn about version control, geoJSON, and GitHub. Check out [github guides](https://help.github.com/articles/good-resources-for-learning-git-and-github/) for additional resources and tutorials
