# Espresso-bootcamp

This bootcamp serves as an introduction point into the Espresso framework and other testing tools for android.


After finishing all tasks of this bootcamp the individual will be able to assist development and QA teams with writing reliable and fast UI tests.

Please refrain from modifying the weather app source code.

For this repo and request evaluation from Vladimir or Joe on each task by messaging them on Slack/hangouts/email.

Software:

    * Android studio
    * Android SDK
    * JDK 1.7 or 1.8


Java knowledge:

    * Beginner for tasks 1-4
    * Advanced for tasks 4-10
          
## Task #1: Setting things up

##### Useful  material and links: 

[Espresso setup instructions] (https://google.github.io/android-testing-support-library/docs/espresso/setup/index.html)


##### Objective:
1. Set up the espresso tests on the sample app provided in the repo
2. Add a test that launches the app and waits (use SystemClock.sleep() to wait)

#####Description:

Using the links above set up an androidTest directory and add your first test. The idea behind having a test that waits to actually see the result.
Remove the test once it's working.

## Task #2: Getting familiar with Espresso API


##### Useful  material and links: 

[Espresso basics tutorial]  (https://google.github.io/android-testing-support-library/docs/espresso/basics/index.html) 

[Espresso api cheat sheet] (https://google.github.io/android-testing-support-library/docs/espresso/cheatsheet/index.html)

##### Objective:
Add a test that opens an overflow menu, selects Settings and verifies that Forecast Preference is displayed for a particular view

#####Description:

To click on items and assert the view you will need to know the identifiers of views. These can be obtained from tools like [uiatomatorviewer](http://developer.android.com/tools/testing-support-library/index.html) or [hierarchy viewer] (http://developer.android.com/tools/help/hierarchy-viewer.html) .

Main difference between two tools is that hierarchy viewer provides you with ENTIRE hierarchy, including items that are not visible, while uiatomatorviewer 
shows only currently visible views which may lead to confusion when asserting with isDisplayed() or doesNotExist().


## Task #3: More of espresso API

##### Objective:
Add a test that Changes the location in settings and verifies that the new location is saved in the settings

#####Description:
Same as #2 this task is just for exploring capabilities of out of the box features of espresso library.
Please don't test anything other than UI. Only validate that settings accepted your change. Don't test network responses and data integrity.


## Task #4: Last one on espresso API

##### Objective:
Add a pull to refresh test. Verify that snackbar is displayed.

#####Description:
Don't test anything other than snackbar.

## Task #5 Understanding onData

##### Useful  material and links: 

[Advanced espresso guide] (https://google.github.io/android-testing-support-library/docs/espresso/advanced/index.html)

##### Objective:
Add a test that changes the  temperature units using onData()

#####Description:

Whenever you encounter a list view in the hierarchy, that is an indication that onView() doesn't work here any more. onView will only work for items that are currently visible on the screen.
However, if an item is off the screen onView will produce view not found exception and fail the test.
onData is different from onView as it doesn't take a view matcher, but data matcher instead. 
Making assertion with onData will automatically scroll to the view if it's not displayed.

Before starting the test think what kind of data the adapter holds in the unit selection dialog. You can write a failing test that will show you data type in the console log.

##  Task #6: Understanding onData part 2:

##### Useful  material and links: 

[Cursor matchers] (http://developer.android.com/reference/android/support/test/espresso/matcher/CursorMatchers.html)


##### Objective:
Pretend that main activity contains a list view that is backed by an adapter that is holding Cursors for each forecast item.

Write a pseudo test that uses onData and clicks on item that has timestamp = today

#####Description:

Use WeatherEntry column names for your test.
Annotate the test with @Ignore so it doesn't run when you run the whole test suite.


## Task #7: RecyclerViews

##### Useful  material and links: 

All links from past tasks.

###### Objective:
Write a test that clicks on last forecast item of the main page.
Don't use position to scroll to the item!



## Task #8: Dagger
##### Useful  material and links: 

#####Objective:



## Task #9: IdlingResources
##### Useful  material and links: 

#####Objective:


## Task #10:
MockWebServer
#####Useful  material and links: 

#####Objective:




