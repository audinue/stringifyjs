# stringifyjs

Readable multiline string in JavaScript.

```javascript
console.log(
	stringify(function() {/*
		Hello world!
		Hello world!
		Hello world!
	*/})
);
```

It is recommended to add a tag--something you put at the beginning of the multiline comment--for it will help future optimization.

```javascript
document.body.innerHTML = stringify(function() {/*html
	<p>Hello world!</p>
	<p>Hello world!</p>
	<p>Hello world!</p>
*/});
```

```javascript
var style = document.createElement('style');
style.textContent = stringify(function() {/*css
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}
	.navigation {
		float: left;
	}
*/});
document.head.appendChild(style);
```

## Usage

Copy and paste the following code to start working:

```javascript
function stringify(s){return(""+s).replace(/^function\s*\(\s*\)\s*{\s*\/\*.*\s*/,"").replace(/\s*\*\/\s*}\s*$/,"")}
```

## Source Code

```javascript
function stringify(f) {
	return (
		f
			.toString()
			.replace(/^function\s*\(\s*\)\s*{\s*\/\*.*\s*/, '')
			.replace(/\s*\*\/\s*}\s*$/, '')
	);
}
```
