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

## Usage

Copy and paste the following code to start working:

```javascript
function stringify(f) {
	return (
		f
			.toString()
			.replace(/^function\s*\(\s*\)\s*{\s*\/\*\s*/, '')
			.replace(/\s*\*\/\s*}\s*$/, '')
	);
}
```
