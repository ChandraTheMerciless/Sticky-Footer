# Sticky-Footer
Want to make a sticky footer in CSS without a framework? Here's one way!

I'm going to show a sample with explanations on how to make a sticky footer in CSS! I've gotten all of this information from other people online, so if this sample helps you out with your work, feel free to take and use it for all of your coding needs! :D

# First things first!

First, let's set up the initial HTML page with some preliminary CSS! The important things to note:
- In the CSS file, both the body and html elements should be set to a height of 100%.
- Create a wrapper for the main body content, with the footer OUTSIDE of this wrapper, and set it to a min-height. Start off with a min-height of 100%.
- I find it easiest to set all html elements (represented by a * in the CSS file) to a margin of 0. Sometimes, html pages will add margins to certain elements, so I like to reset that to 0 at the beginning of my css file, and then add margin spacing below as needed.

index.html file:

```
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <link rel="stylesheet" type="text/css" href="style.css">
    </head>
    
    <body>
        <div class="wrapper-height">
            <p></p>
        </div>
        
        <footer>
            <span>footer</span>
        </footer>
    </body>
</html>
```


style.css file:

```
*{
    margin:0;
}

html{
    height:100%;
}

body{
    height:100%;
}

.wrapper-height{
    min-height:100%;
}

footer{
    /*extra styling to make footer visible*/
    background-color:darkmagenta;
    color:white;
    text-align:center;
    padding:5px;
}
```

# Fixing the footer placement with calc!

CSS3 has a new property for sizing called "calc." This will allow you to mathematically calculate where the footer should stick while keeping the 100% height. The problem with trying to specify a min-height of a different percentage is that when a user zooms in or out, the footers bottom will travel up or down the page, creating an unnecessary scroll bar when the user zooms in.

There is one down-side to this method: If your footer has a different color from the rest of the web page, you might notice the bottom jumping up and down by a few pixels as you zoom in and out. But if you are designing a website whose footer is the same color as the body and css, you can have it floating a few pixels above where it needs to stick, to prevent a scroll bar from appearing unnecessarily as the user zooms in and out.

Or, if the footer is a different color, you can give the body the same background-color as the footer, and then give the wrapper around the main body content a different background-color. Then, when the footer's bottom jumps higher than the bottom of the page, the gap will be hidden.

This is not a perfect technique, but it's an easy fix that's not too hacky, and for quick development, it might be a good option for your project :).

Last things to note:
- If you add a top or bottom margin or padding to the outside wrapper with a min-height, it will alter the footer's placement. But if you add a second wrapper inside, and add padding and margin spacing to that, it will not affect where the footer sticks.

The "finished" preliminary code is below!

index.html file:
```
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <link rel="stylesheet" type="text/css" href="style.css">
    </head>
    
    <body>
        <div class="wrapper-height">
            <p>Some content on the page!</p>
            <p>Some more content!</p>
        </div>
        
        <footer>
            <span>footer</span>
        </footer>
    </body>
</html>
```

style.css file:
```
*{
    margin:0;
}

html{
    height:100%;
}

body{
    height:100%;
    background-color:darkmagenta;
}

.wrapper-height{
    min-height:calc(100% - 34px);
    background-color:white;
    font-size:30px;
}

.wrapper-height p{
    padding-left:2em;
    padding-top:1em;
}

footer{
    /*extra styling to make footer visible*/
    background-color:darkmagenta;
    color:white;
    text-align:center;
    padding:5px;
}
```


# Sources
Sticky Footer by Ryan Fait
http://ryanfait.com/

A Pen By David Conner: Pure CSS Sticky Footer
http://codepen.io/davidicus/pen/BenLl
