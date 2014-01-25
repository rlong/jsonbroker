---
layout: default
---

Css Tips
====
**document-version:  0.0.2014.01.25 (pre-alpha)**  


###Disable text selection on elements acting as buttons

Disable text selection on elements acting as buttons (does not work on android (version 4.0.4)):

	-webkit-touch-callout: none;
	-webkit-user-select: none;
	-khtml-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;
	user-select: none;


An example: 

	<style type="text/css">
		html {
			-webkit-touch-callout: none;
			-webkit-user-select: none;
			-khtml-user-select: none;
			-moz-user-select: none;
			-ms-user-select: none;
			user-select: none;
		}
	</style>


references:

* [cross browser - CSS rule to disable text selection highlighting - Stack Overflow](http://stackoverflow.com/questions/826782/css-rule-to-disable-text-selection-highlighting)

----
###Remove grey hilighting when tapping links


	<style type="text/css">
		html {
			-webkit-tap-highlight-color: rgba(0,0,0,0);
		}
	</style>


references:

* [CSS property: -webkit-tap-highlight-color](http://css-infos.net/property/-webkit-tap-highlight-color)
* [Quick Tip: Customizing the Mobile Safari tap highlight color - YUI Blog](http://www.yuiblog.com/blog/2010/10/01/quick-tip-customizing-the-mobile-safari-tap-highlight-color/)
* [Remove Gray Highlight When Tapping Links in Mobile Safari | CSS-Tricks](http://css-tricks.com/snippets/css/remove-gray-highlight-when-tapping-links-in-mobile-safari/)

----
###Prevent font scaling in landscape mode


	<style type="text/css">

		html {
			-webkit-text-size-adjust: 100%;
		}
	</style>

references:

* [css - Fonts become bold when changing orientation - Stack Overflow](http://stackoverflow.com/questions/10775895/fonts-become-bold-when-changing-orientation)
* [Preserve HTML font-size when iPhone orientation changes from portrait to landscape - Stack Overflow](http://stackoverflow.com/questions/2710764/preserve-html-font-size-when-iphone-orientation-changes-from-portrait-to-landsca)
* [CSS property: -webkit-text-size-adjust](http://css-infos.net/property/-webkit-text-size-adjust)

----
###Conditional application of CSS rules based on screen height

Useful for detecting device category (handheld, tablet, desktop) and orientation of the device:

    <style type="text/css">

        /* for handhelds with a small vertical height (e.g. iPhone in landscape) ... */
        @media screen and (max-height: 300px) {

            .button_image {
                height: 10%;
                max-height: 10%;
                width: auto;
            }
        }
    </style>
