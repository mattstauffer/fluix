# Fluix


## Example HTML
```html
<div class="whatever-wrapper">
    <div class="whatever">1</div>
    <div class="whatever-foo">2</div>
    <div class="whatever-bar">3</div>
</div>
```

## Example SCSS
```scss
.whatever-wrapper {
	@include split(10em, 100%, 10em) {

		// Fixed column of 10em
		.whatever {
			background: red;
		}

		// Fluid column of 100% remaining
		.whatever-foo {
			background: blue;
		}

		// Fixed column of 10em
		.whatever-bar {
			background: yellow;
		}
	}	
}
```

## Output
http://dev.j3rn.org/
