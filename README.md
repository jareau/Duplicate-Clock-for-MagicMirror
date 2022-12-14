I have a 32" screen hanging on a wall in the kitchen that displays MagicMirror.  The overall intention is to provide the family with memories, information, and conversation starters. The screen needs to be legible from far away, so very large text is a must, which basically means I don't have a lot of space for lots of modules on a single screen. 

The [MMM-Carousel](https://github.com/barnabycolby/MMM-Carousel) module cycles through slides, which solves my real estate problem.

Here's an example of the slides I'm running: 
* Slide 1
 -- [MMM-Google Photos](github.com/hermanho/MMM-GooglePhotos), I cycle through family pictures in full screen.
-- the default [clock](https://docs.magicmirror.builders/modules/clock.html) module, as a digital clock
-- the default [newsfeed](https://docs.magicmirror.builders/modules/newsfeed.html) module

* Slide 2
--  [MMM-OpenmapWeather](https://github.com/sathyarajv/MMM-OpenmapWeather), I like their colorful icons
-- the default [weather](https://docs.magicmirror.builders/modules/weather.html) module to display the weather forecast 
-- [MMM-DarkSkyRadar](https://github.com/vincep5/MMM-DarkSkyRadar) to display live rain radar

* Slide 3 
-- [MMM-MonthlyCalendar](https://github.com/kolbyjack/MMM-MonthlyCalendar) that shows our family calendar and a [National Day Calendar](https://natdaycal.wordpress.com/), which is nice to strike up conversation with the kids. 

* Slide 4 = a duplicate of the default [clock](https://docs.magicmirror.builders/modules/clock.html) module
-- the wife asked for an analog clock face to help our small kids practice reading an analog clock. 
-- She shared a link to an amazon "learning clock", which I recreated as per the specs needed by the clock module for clock faces.
-- This is helpful for that, and slide 1 cycles next, which helps them confirm whether they read the analog clock face correctly. 
-- here's my clock face file: 
![learning-clock](https://user-images.githubusercontent.com/7671154/207639614-0dfce5e5-032f-4b2c-a2f9-4f50594705a8.svg)

Here's how I did it:
* copy the default clock module from the *modules/default* folder, and paste it into the *modules/* folder
* rename the folder to *clock2*
* open the folder
* rename the css file to *clock2_styles.css*
* rename the *clock.js* file to *clock2.js*
* open the *clock2.js* file
* change line 9 from
-- Module.register("clock", {
-- to 
-- Module.register("clock2", {
* change line 14 from
-- return ["clock_styles.css"];
-- to 
-- return ["clock2_styles.css"];
* over in the *config.js* file, copy/paste the *clock* module, and name it *clock2*, change the seconds hand color, choose 
* in my case, I then added a new slide to MMM-Carousel, and configured it to only display the analog clock, in full screen.
* the css in clock2_styles was modified to show thicker hour and minute hands in different colors. 

Here is a screen grab of the  end result:
![Screen Shot 2022-12-14 at 10 17 18 AM](https://user-images.githubusercontent.com/7671154/207639801-1aa6c865-c950-42d1-b4dc-42746148716c.jpg)
