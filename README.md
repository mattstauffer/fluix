# Fluix

A Sass/SCSS mixin for quickly and simply generating mixed fluid/fixed grids. Under active development.

Issuse: https://github.com/jeroengerits/fluix/issues

## General Usage
```scss
// Wrap columns with the split; the number of arguments to split should be
// the same as the number of columns.
@include split(10em, 100%) {
	.fixed-width-left-column {
	}
	.fluid-width-right-column {
	}
}
```

## Usage Options
```scss
// Only fluid columns
@include split(50%, 50%){}

// Only fixed columns
@include split(10em, 10em){}

// Mixed columns
@include split(100%, 1em){}

// Many columns
@include split(100%, 1em, 1em, 1em, 1em, 1em, 1em, 1em){}

// Multiple fluid and fixed column sizes
@include split(30%, 70%, 1em, 5em){}

// EM, REM and PX support
@include split(100%, 1em, 5em){}
@include split(100%, 50px, 100px){}
@include split(100%, 1rem, 5rem){}

// Mixed fixed widths are not supported
@include split(100%, 3em, 1rem, 10px){} // Invalid

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
	@include split(10em, 100%, 10em) {

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
```

## Real live Example

```html
<div class="author">
	<div class="avatar">
		<img src="/avatar.jpg">
	</div>
	<div class="name">
		John Doe
	</div>
</div>
```

```scss
// Nesting syntax
.author {
	@include split(5em, 100%) {
		.avatar {
			// do stuff
		}
		.name {
			// do stuff
		}
	}
}

// Alternative non-nesting syntax
.author {
	@include split(5em, 100%);
	.avatar {
		// do stuff
	}
	.name {
		// do stuff
	}
}
```

## Compatibility note
Combining fluid and fixed widths requires CSS calc(), which is unavailable on IE < 9.