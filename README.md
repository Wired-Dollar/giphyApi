# giphyApi

Everything is loaded and the data pulled then the $(doc).ready(function()) is called. This puts the action into all the components of the app. 

This is the list of options we start with:

var cartoons =["roadrunner", "bugs bunny", "tweety", "mickey mouse", "scrooge mcduck", "alvin and the chipmunks", "spongebob squarepants", "ed, ed, and eddie", "maya and miguel","casper"]

This is our API setup:

var query = $.get("http://api.giphy.com/v1/gifs/search?q=ryan+gosling&api_key=YOUR_API_KEY&limit=10");
query.done(function(data) { console.log("success got data", data); });

var cartoons has buttons, user clicks a button and the API setup does a query call for 10 images with two states each:

a still
"https://media1.giphy.com/media/cZ7rmKfFYOvYI/200_s.gif"
and an animated
"https://media1.giphy.com/media/cZ7rmKfFYOvYI/200.gif"

at first load the still image is shown, with the on.click from user the image is switched to the animated gif. There may be a need for prevent default function here to stop the page from reloading.

There will be an input box that has a button by it for the user to add another item. User input on the box will do another API pull for the new item and add that item to the list of boxes at the top. There could be a safety measure added here... an if/ else... since our array contains only cartoons, query the API to see if item requested is labeled under cartoons with Giphy.com and if that is true then add the item as mentioned if false then alert the user "please add a valid cartoon" or something like that.

