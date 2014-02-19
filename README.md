# Fluix


## Example HTML
´´´
    <div class="whatever-wrapper">
        <div class="whatever">1</div>
        <div class="whatever-foo">2</div>
        <div class="whatever-bar">3</div>
    </div>
´´´

## Example SCSS
´´´
.whatever-wrapper {
	@include split(10em, 100%, 10em) {
		.whatever {
			background: red;
		}
		.whatever-foo {
			background: blue;
		}
		.whatever-bar {
			background: yellow;
		}
	}	
}
´´´

## Output
´´´
	http://dev.j3rn.org/
´´´