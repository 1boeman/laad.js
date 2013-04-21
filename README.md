laad.js
=======

Pretty simple asynchronous script loading - laad.js

JavaScript script loading libraries  (yep-nope.js, require.js, Lab.js, head.js $script.js, etc.js, etc.js) are quite  ubiquitous nowadays.  
In fact there's so many that the time it takes to compare them all is more than enough to write your own.

Here's mine.
It limits itself to the most basic of tasks, namely loading and executing scripts.

The code below will load any files requested only once, and use the internally cached version afterwards until page refresh. 

Simple to sum up:

Load a script asynchronously, with callback:
```javascript

laad.js('path/to/script.js',function(){
	alert('loaded');
})

```

or without callback:
```javascript
laad.js('path/to/script.js')
```

Load another script but wait for the previous script to finish loading (for dependency's sake):

```javascript
laad.wait('path/to/script2.js',function(){
	alert('loaded');
})
```

add a bunch of (mutually independent(!)) scripts asynchronously and execute a single callback when they've all finished loading:


```javascript
laad.js(['path/to/script2.js','path/to/script3.js','path/to/script4.js'],function(){
	alert('loaded all of them');
})
```


