# Sticky-Footer
Want to make a sticky footer in CSS without a framework? Here's one way!

I'm going to show a sample with explanations on how to make a sticky footer in CSS! I've gotten all of this information from other people online, so if this sample helps you out with your work, feel free to take and use it for all of your coding needs! :D

# First things first!

First, let's set up the initial HTML page with some preliminary CSS!

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