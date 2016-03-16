# Ladda for Bootstrap 3


Buttons with built-in loading indicators, effectively bridging the gap between action and feedback.

<a href="http://msurguy.github.io/ladda-bootstrap/" target="_blank"> Check out the demo page.</a>

###Installation

``` 
$ bower install bootstrap-loading

in /bower.json file insert:
"dependencies": {
    "ladda-bootstrap": "https://github.com/msurguy/ladda-bootstrap.git#^0.1.0"
  }

```

######or:

*not need to enter anything /bower.json file, this command does this automatically.*

``` $ bower install bootstrap-loading --save-dev ```


###HTML

Ladda buttons must be given the class ladda-button and the button label needs to have the ladda-label class. The ladda-label will be automatically created if it does not exist in the DOM. Below is an example of a button which will use the expand-right animation style.

``` <button class="ladda-button" data-style="expand-right"><span class="ladda-label">Submit</span></button> ```

###Buttons accepts three attributes:

* data-style: one of the button styles, full list in demo [required]
* data-color: green/red/blue/purple/mint
* data-size: xs/s/l/xl, defaults to medium
* data-spinner-size: 40, pixel dimensions of spinner, defaults to dynamic size based on the button height
* data-spinner-color: A hex code or any named CSS color.

###JavaScript

If you will be using the loading animation for a form that is submitted to the server (always resulting in a page reload) you can use the bind() method:

```
// Automatically trigger the loading animation on click
Ladda.bind( 'input[type=submit]' );

// Same as the above but automatically stops after two seconds
Ladda.bind( 'input[type=submit]', { timeout: 2000 } );
If you want JavaScript control over your buttons you can use the following approach:

// Create a new instance of ladda for the specified button
// Please note that this must be done after the button has been
// added to the DOM.
var l = Ladda.create( document.querySelector( '.my-button' ) );

// Start loading
l.start();

// Will display a progress bar for 50% of the button width
l.setProgress( 0.5 );

// Stop loading
l.stop();

// Toggle between loading/not loading states
l.toggle();

// Check the current state
l.isLoading();
All loading animations on the page can be stopped by using:

Ladda.stopAll();
```

######Original Ladda buttons concept originally by @hakimel, example using Bootstrap 3 by @msurguy, adapted to the bower package manager for @isaahmdantas. 

