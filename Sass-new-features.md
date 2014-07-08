http://alistapart.com/article/dry-ing-out-your-sass-mixins

### Placeholders

> Placeholder selectors are a unique kind of selector for use with Sass’s @extend directive. Written like a class, but starting with a % instead of a ., they behave just like a normal extend except that they won’t get printed to the stylesheet unless extended. Just like normal extends, the selector gets placed in the stylesheet where the placeholder is declared.

````
Sass
%foo {
	color: red;
}

.bar {
	@extend %foo;
	background: blue;
}

.baz {
	@extend %foo;
	background: yellow;
}
CSS
.bar, 
.baz {
	color: red;
}

.bar {
	background: blue;
}

.baz {
	background: yellow;
}
````

### MAPS
> Maps are a data type (like numbers, strings, and lists) in Sass 3.3 that behave in a similar way to objects in JavaScript. They are comprised of key/value pairs, where keys and values can be any of Sass’s data types (including maps themselves). Keys are always unique and can be retrieved by name, making them ideal for unique storage and retrieval.

```` Sass
$properties: (
	background: red,
	color: blue,
	font-size: 1em,
	font-family: (Helvetica, arial, sans-serif)
);

.foo {
	color: map-get($properties, color);
}
````