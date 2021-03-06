E2 Workbench Podcast 4 - Google Chrome UCM Search Extension

Source on GitHub

Enterprise Content Management systems are great for the classification, storage and retrieval of information, but you have to navigate to them.  Oracle's Universal Content Management technology has a great Desktop Integration Suite to allow for search and retrieval of UCM information outside of the actual CMS, but my laziness reached new levels this past week - I wanted to search directly from my Google Chrome browser window, without opening the web interface for UCM.

The solution?  I decided to take a look at what it would take to use the service oriented nature of UCM to create an extension for Google Chrome.  After a few hours of development and a few cups of coffee I ended up with an extension that allows a search to be executed from and results displayed within an extension dialuge.  To make this all possible, the extension leverages
1. HTML5 Localstorage
2. UCM's JSON functionality
3. Chrome Extension Package

Architecture of a Google Chrome Extension
IMHO Google made a very smart choice by leveraging client side web technologies for extension development.  I was able to take my knowledge of HTML, CSS and JQuery, applying them to create this extension.
1. manifest.JSON - the configuration file for your extension.  Check out all of the details (http://code.google.com/chrome/extensions/manifest.html)
2. search.html (generally popup.html) - this is a "content" page in the extension and provides us with the inteface when the extension toolbar buttion is clicked
3. options.html - this will allow us to save the UCM server value using HTML5 localstorage
4. background.html - critical in creating an interface for the search.html file to access the localstorage values.  The background.html file runs as a background processes within Chrome and is used as a mediator between "content" pagees like search.html
5. javascript / images / css - nothing new here, other than the usual for web development :-)

Ingrediants for our Chrome Extension
I was able to create the extension so quickly due to great work from other people in the community.  I would like to express my thanks to
Awesome JQuery library by Bex Huff (*************) that allows for straightforward access to the JSON response from UCM
Tablesorter JQuery extension (http://tablesorter.com/docs/)
HTML5 LocalStorage APIs (http://www.rajdeepd.com/articles/chrome/localstrg/LocalStorageSample.htm)
How to Build a Chrome Extension (http://julianapena.com/2010/01/how-to-build-a-chrome-extension-part-1-basics/)
Function Icon Set (http://wefunction.com/2008/07/function-free-icon-set/)

Some serious gotchas
1. Issue with caller.... - FireFox will not show this error in its JS console, but Chrome will

Please note that this is a personal sample extension and not one that is supported by Oracle.

Link to chrome extension on Google
