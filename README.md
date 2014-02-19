# Fluix

Under development

## Usage
```scss

// Only fluid
@include split(50%, 50%){}

// Only fixed
@include split(10em, 10em){}

// Mixed arguments
@include split(100%, 1em){}

// Unlimited columns
@include split(100%, 1em, 1em, 1em, 1em, 1em, 1em, 1em){}
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

		// Fluid column of 100%
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
.author {
	@include split(5em, 100%) {
		.avatar {
			img { width:100% }
		}
		.name {
			font-weight:bold;
		}
	}
}
```