MerryGoRound
============

A fully-automated, flexible, customizable carousel class for Mootools. 

Pass it an element with some children and it will figure out where to put the page breaks
to show the maximum number of elements per scroll, without skipping any. This even works
if the elements all have different widths.

It will inject the next/previous buttons for you (customizable), and will 
optionally generate pagination controls and inject those as well.

The options for all of the control elements and the Fx used can be specified, 
although reasonable defaults are already in place. Styling is up to you though.

![Screenshot](http://idisk.me.com/iancollins/Public/Pictures/Skitch/Barack_Obama_-_Powerset-20091013-124144.png)

How to use
----------

The easiest setup possible:

	new MerryGoRound(element);

Given that element contains some children, MerryGoRound will wrap element with a 
container element (configurable), then size element to be the sum of its children's 
widths and margins. Next it calculates which elements to scroll to when the next/previous
buttons are pushed. It then injects the next/previous buttons and optionally the 
pagination controls. 

An example that uses some options:

	new MerryGoRound(element, {
		per_page      : 2, 
		cycle         : true,
		page_controls : true,
		selector      : 'li'
	});
	
What changes with this MerryGoRound is:

1. When clicking next/previous only two elements are shifted at a time.
2. When reaching the end/start the buttons stay and allow you to wrap around.
3. Pagination controls are created and injected (see screenshot above).
4. Only the li tags directly inside of element will be used.

Sytax
-----

	new MerryGoRound(element, [options])
	
Arguments
---------

	1. element - (mixed) An Element or an id string.
	2. options - (object, optional) the options described below:
	
Options
-------

* selector        : (string) Selector to pass to element.getChildren to determine scrolling elements. Defaults to '*'.
* cycle           : (boolean) Pass true to keep next/previous controls when at the star/end. Defaults to false.
* per_page        : (number) How many elements to scroll on next/previous. Defaults to 'auto'.
* page_controls   : (boolean) Pass true to inject page controls. Defaults to false.
* fx_options      : (object) Options to pass to Fx constructor.
* wrapper_width   : (number) Width of carousel. Defaults to width of element passed.
* wrapper_height  : (number) Height of carousel. Defaults to height of element passed.
* wrapper_tag     : (string) Tag for wrapper. Defaults to div.
* wrapper_options : (object) Options to pass to Element constructor.
* button_event    : (string) Event for next/previous buttons. Defaults to 'click'.
* previous_button\_tag     : (string) Tag for buttons. Defaults to 'a'.
* previous_button\_options : (object) Options to pass to Element constructors.
* next_button\_tag         : (string) Tag for buttons. Defaults to 'a'.
* next_button\_options     : (object) Options to pass to Element constructors.
* current_page\_class : (string) Class for active pagination marker. Defaults to 'merry-go-round-current-page'.
* page_controls\_tag     : (string) Tag for pagination element. Defaults to 'div'.
* page_controls\_options : (object) Options to pass to pagination Element constructor.

Events
------

* pageShown : The function to execute when the a page is shown.
							Gets passed the page index and the instance of MerryGoRound.