### MAPS#section10
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