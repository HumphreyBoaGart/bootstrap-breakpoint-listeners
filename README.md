#Bootstrap Breakpoint Listeners for jQuery
Creates the function `checkLayout()` to give a simple cut-and-paste solution for firing off javascript based on which Bootstrap layout is being displayed. It kicks off automatically on page load, and also whenever the browser window is resized, which I've found to be handy as hell when you need to kick off functions to fix UI bugs moving from vastly different mobile/tablet/desktop layouts.

I'm not sure why something like this isn't built into Bootstrap, or if it is, it's not documented at all.

###Implementation
Include the contents of `template.html`, `styles.css`, and `checkLayout.js` in your html, css, and javascript. Rather than calculating screen width, this function simply checks the `display` style of the four `.check-layout` divs. As such, it should still work without modification if you've really changed up when/where Bootstrap's media queries kick off.

It also includes a throttle timer on the `$(window).resize();` event, which I don't recommend getting rid of if your project plans on seeing traffic or serious production.

Also protip, you may want to be using `event.stopPropagation();` on the `setLayout*()` functions if you have other listeners for functions called within - sloppy functions bubble up fast. Hell, I'm pretty sure there's a cleaner way to do this one, but it's working for the project it was needed for.
