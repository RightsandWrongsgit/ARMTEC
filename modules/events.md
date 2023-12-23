
# Calendar & Events

<br>

One of the most basic interactions you will have with a calendar is to "Book" something; a room, a meeting, an event, etc.   Drupal.org provides a [review of the main options.](https://www.drupal.org/docs/extending-drupal/contributed-modules/comparison-of-contributed-modules/comparison-of-bookingavailabilityreservation-modules)  Here a combination of two calendar related modules and another that integrates nicely with them is presented.

## Bookable Calendar
[The Bookable Calendar module](https://www.drupal.org/project/bookable_calendar) is the workhorse component.  It is here where you can establish what is bookable (room, course, etc.), who can book it, for how long, how many days/weeks/months into the future, for how many people, etc.  One of the better videos on [what can be done with the bookable calendar is here.](https://www.youtube.com/watch?v=UFnQnwfg-44)

[The Calendar View module](https://www.drupal.org/project/calendar_view) is then your choice for the display of your calendar information.  And just like [Views](modules/views.md), you do various set up selections for titles, what is displayed, etc.  However, what you are now working with is a template(s) for the views you start working with and that makes the choice options more calendar relevant out of the box.

The Bookable Calendar module can also be combined with the rules type of logic that the [Events→Conditions→Actions](../modules/ECA.md) can provide.

<br>

## Events: The kind you run

Just to make sure you are where you think you are, this page is about how to use Drupal to set up an calendar type of event.  There is a whole different page explaining the [Events→Conditions→Actions](../modules/ECA.md) which is a toolset that triggers an action to occur under events and conditions as a set of rules.  

It should not be surprising at all the Drupal has a rich starting point to set up an event website.  This is because Drupal is very community oriented and runs all sorts of events around the globe throughout the year.  Since the Drupal community needs its own websites to manage these events, they have built some really great functionality.

## Demo

The easiest way to see what is available is to [watch a video overview demonstration](https://www.youtube.com/watch?v=1q5VqBSJVEM)

## Event Platform module

You can find the [Event Platform module](https://www.drupal.org/project/event_platform) on the Drupal site.  Use the normal composer method to install the module and drush to enable it.

`composer require 'drupal/event_platform`<br>
`drush en event_platform`

<br>
<br>
<br>

[Learn More - Drupal Modules List](../chapters.md#drupal-modules)
