
# 'Add Your Own' button

How to create the "Add Your Own" Button & place it in the Social Bar







We want a button over in the "Social Bar" in the left side of the Olivero theme.  As we set it up, we are just going to direct it to "google's URL" as the link.  But our objective is to eventually direct it to a page of User Submission options for travel destinations, events, routes, CFI and A&Ps, FBO's, Chambers of Commerce, etc.  The node that it will point to will be built and added to over time to take submissions from an increasingly broad range of things; and a headline/summary/and form link unique to each type of submission will be present on this master submission page this button is linked to.









We are going to make our button as a custom block and it will be in the custom block library for us to ultimately "place" it (e.g. put in the 'region' of our layout where we want it).


The first time we go into that custom block library we hit "add" and give it a name.  Each time we might want to work it to do things like change size, color, font style, etc. we find the name on the list and hit "edit".


The screen we see looks like this.  The key is to go down to the box below the Body where it says "Text Format" and select "Full HTML" from the options on the pulldown. Since this is an 'edit' view, we already see the button but how we make it is with HTML code and we are going to look at that.

You hit the "Source" button in the upper right of the Body area and this is where you place the HTML code to do stuff.  In our case, since it is a button that doesn't have a bunch of graphical interface with other elements of our website, just within the 'region' we place it, we are going to <style> the look of the button right within a leading chunk of inline CSS code.

The code scrolls in that window, so here you see it in three screen shots. The code itself is available right below so it can just be copied from this documentation and dropped in the 'Body' area:

<img src="../theme/themeimages/oliverobuttoncss.png"  width="600">

The button that makes up the code won't show up on your website until you 'place' the custom block you made.  To do that you go into "Structure-Block Layout" from your administration tool bar and you will see all the regions you have in your site.  Scroll down to the region called 'Social Bar' and hit the "Place Block" button; where upon you will see a list of the blocks available.  You named this block when you set it up as "Add Your Own Button", so select that to place.  It may drop in below the RSS Feed that is a standard item in this region but all you need to do is drag and drop it above that with the Maltese cross looking symbol.

In that last line of code you see the 'formaction=" and once you have your URL address for the 'node' in your site where the list of submissions people can make is located, you just need to edit to that from the google address used in this initial set up.



