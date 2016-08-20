# jquery-scrollspy

A jQuery plugin for detecting enter/exit of elements in the viewport when the user scrolls.

## New Features

Added a couple new features:

 * Aug 2016 - stop to spy with the `stopScrollSpy` method, add the `scrollSpyOptions` method to get/set options
 * May 2014 - optional window offset, allows for things like floating navs
 * Feb 2014 - supports window resize
 * Nov 2013 - throttles scrollspy events so that event handles only fire every 100 milliseconds

## Usage

```js
$('.tile').on('scrollSpy:enter', function() {
	console.log('enter:', $(this).attr('id'));
});

var i = 0;

$('.tile').on('scrollSpy:exit', function() {
	console.log('exit:', $(this).attr('id'));

	if (i >= 3) {
		// when this event fired for the third time, we stop to spy this element
		$('.tile').stopScrollSpy();

		// or you could do this:
		// $.stopScrollSpy($('.tile'));
		// or this
		// $('.tile').each(function(i, element) {
		// 		$.stopScrollSpy(element);
		// });
	}
	++i;
});

$('.tile').scrollSpy();

// or you could do this:
// $.scrollSpy($('.tile'));
// or this
// $('.tile').each(function(i, element) {
// 		$.scrollSpy(element);
// });

```

# Window Resize

Use the ```scrollSpy:winSize``` event for watching window resize.  This fires any time the window is resized by the user.

```
$.winSizeSpy().on('scrollSpy:winSize', funcy)
```

# Contributions

Please provide pull requests for additional features.  Test cases would be most weclome!

Thank you contributors:

 * [@Mithgol](https://github.com/Mithgol)
 * [@eithanshavit](https://github.com/eithanshavit)
