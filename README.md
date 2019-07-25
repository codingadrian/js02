# JS01 - Drum Kit

This is the first project for [#javascript30](https://javascript30.com/)

## Author
My name is [Adrian](https://github.com/codingadrian). I am a 32 y.o. Costa Rican. I am working to become a full stack developer.

## Goal

* To complete the 30 days challenge for JavaScript.
* To read about the methods, functions, and others I see while in the code-along. So that I can understand instead of just copying.
* To document in each day's README, what I did and what I learned

## Project structure:

Each day/project will have its own GitHub Page.

The directory for each day/project will be composed of:

* mainFolderDay#
  * index.html
  * images/
    * if any***
  * script/
    * the script file
  * styles/
    * the css file
  * others/
    * audios, videos and/or others


I will push through GitHub at the end of each day, and maybe several "pushes" throughout the day.

## What I did and what I have learned

* The clock is composed of an outter div which is made a circle with CSS, the another div containing the clock hands, also a pin that "holds" the hands.

* The box-sizing is set to border box, as to try to gain control over how the mark-up is displayed.

* The image is set to the html tag, set to no-repeat so that it extends through size I have given it, in this case 100% of vh and vw.

* The body tag is given the flex display, sized to my 95vh (this avoids the scroll bar added, I guess there is a minor difference between the html and the viewport) and to align its items to the center.

* The .clock is made into a circle with the width, height and border-radius technique, centered with the margin-auto technique, the position is set to relative.

* The hands are set to an absolute position with reference to the top by 50%. I used the transform to rotate it in a 90deg angle and transform-origin to change the axis to the right, this makes it seem as it is moving from the far right instead of the middle.

* Using transition I can gradually apply changes and with the timing-function I can change the "efect" in which those changes are applied.

* The pin is set to relative and made round with the border-radius technique.

* The hands are given color with basic color names.

* The last lines of CSS are for the clock face, and uses the transform set to translateY which is just a way to move elements relative to their previous position.

* For JS I start by learning "cache your object", this is done for browser performance, this practice stores repeatedly accessed objects inside a user defined variable, what this means is I can write up a shorthard for long code and spead up loading at the same time.

* I start with a function with the name setDate(). Now I set a var to an object with the Date() method.

* I store the seconds in a const, by applying the getSeconds() method to the now variable, this also happens for minutes and hours.

* I then set a const for the degrees. This requires math: divide the minutes by its correspoding time value, so for minutes 60, for hours 12 (not 24 because it is an analog clock), then multiplied by 360 (the number of degrees in a circle) and then add 90 (this 90 is because of the 90deg rotate I applied to the hands to make the time start counting from the 12h position instead of the 9th), this will provide the position in degrees of where the clock hand should be pointing to, or the position where it has to move.

* The last line of that code block is for applying animation. This is where the "cached objects" are used, by suffixing style.transform to the "degree location" in the clock.

* The glitch: when the seconds hand reaches the 12 position, it goes backwards and counter clockwise to the 12 and starts over, this should not be the normal behavior of a clock. This I investigated and I found a post on Medium, where Mr. Ekkel uses a  if...else statement to fix the issue. He creates a const for allHands to select all elements with the class of hand, then he creates a if...else stament so that when secondsDegrees equal 90 the transition element is set to none else it is set to empty, reverting back to the code in the stylesheet (adding the animation again).

* setInterval is I think the "heart" of the clock, I pass through it the setDate function created above, and the interval, this means, how often do we want to refresh the date, it is set to 1000ms, this means the seconds hand, will move every second just like a clock.

* Fixing the glitch by copying someone else code did not feel right, but I made sure I had understood what I was copying and that it became a lesson.