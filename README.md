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
Will result in a fixed | fluid | fixed grid
```scss
.whatever-wrapper {
	@include split(10em, 100%, 10em) {

		// Fixed column of 10em
		.whatever {
			background: red;
		}

		// Fluid column of 100%
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

## Other usage
```scss

// Only fluid
@include split(50%, 50%){}

// Only fixed
@include split(10em, 10em){}

// Unlimited columns and mixed arguments
@include split(50%, 50%, 1em, 1em, 1em, 1em, 1em){}

