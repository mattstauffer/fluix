# Fluix

A Sass/SCSS mixin for quickly and simply generating mixed fluid/fixed grids. Under active development.

Issues: https://github.com/jeroengerits/fluix/issues?state=open

## General Usage
```scss
// Mix fluid and fixed columns
@include columns(10em, 100%) {
	.fixed-width-left-column {
	}
	.fluid-width-right-column {
	}
}
```

## Usage Options
```scss
// Only fluid columns
@include columns(50%, 50%) {}

// Only fixed columns
@include columns(10em, 10em) {}

// Mixed columns
@include columns(100%, 1em) {}

// Many columns
@include columns(100%, 1em, 1em, 1em, 1em, 1em, 1em, 1em) {}

// Multiple fluid and fixed column sizes
@include columns(30%, 70%, 1em, 5em) {}

// EM, REM and PX support
@include columns(100%, 1em, 5em) {}
@include columns(100%, 50px, 100px) {}
@include columns(100%, 1rem, 5rem) {}

// Mixing fixed width units is not supported
@include columns(100%, 3em, 1rem, 10px) {} // Invalid

```

## Example

Will result in a 3 column _fixed | fluid | fixed_ grid.

**HTML**

```html
<div class="whatever-wrapper">
    <div class="whatever">1</div>
    <div class="whatever-foo">2</div>
    <div class="whatever-bar">3</div>
</div>
```

**SCSS**

```scss
.whatever-wrapper {
	@include columns(10em, 100%, 10em) {

		// Fixed column of 10em
		.whatever {
			// add scss
		}

		// Fluid column of 100% (fills remaining space)
		.whatever-foo {
			// add scss
		}

		// Fixed column of 10em
		.whatever-bar {
			// add scss
		}
	}
}

// Alternative non-nesting syntax
.whatever-wrapper {
	@include columns(10em, 100%, 10em);
	.whatever {}
}
```

## Examples

Check more examples in the /examples folder.

## Compatibility note

Combining fluid and fixed widths requires CSS calc(), which is unavailable on IE < 9.
