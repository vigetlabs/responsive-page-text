# Responsive Page Text

> Mixins for LESS and Sass (.scss) to make all page text —font sizes and line heights— responsive


Set your font-sizes and line-heights with these mixins, set a mobile scale factors for font size and line height if you want to (or use the defaults), and all text on your page will scale down automagically.

Want some text to scale differently? Use a media query to give that text a different full-size value for mobile.

Want some text to always stay the same size? Want some text to keep its font size while scaling its line height? Want some text to keep its line height while scaling its font size? Just don't use the mixin for the things you want to keep constant, or override the mixin with an explicit style.

## Demos:

- LESS: https://codepen.io/henry/pen/brOzZw?editors=1100
- Sass (.scss): https://codepen.io/henry/pen/qXLwZa?editors=1100

	![responsive-page-text](https://user-images.githubusercontent.com/3282350/29940024-e200b6ac-8e5b-11e7-8584-ecc71c6e6abf.gif)

## Usage

1. Set variables

	name | argument | default | what is it?
	-----|----------|---------|------------
	`fz` | `{number}`, unitless | `14` | page base font-size (e.g. for 14px, `14`)
	`lh` | `{number}`, unitless | `18` | page base line-height (e.g. for 18px, use `18`)
	`mobile-font-size-factor` | `{number}`, unitless | `.74` | the factor by which to scale font size on mobile
	`mobile-line-height-factor` | `{number}`, unitless | `mobile-font-size-factor * 5/4` | the factor by which to scale line height on mobile

2. Style with the font-size and line-height mixins

	mixin | argument | default | what does it do?
	------|----------|---------|-----------------
	`fz()` | `{number}` <br> pixel font size / 1px | `fz` | sets font size
	`lh()` | `{number}` <br> ratio of line height to font size | `lh` | sets line height
	`fzlh()` | `{number,number}` <br> arg1: unitless font size <br> arg2: unitless line height | `fz, lh` | shorthand to set both `fz()` and `lh()`

	### Examples

	- Setting font size to 20px and line height to 24px:

		```less
		// LESS
		my-target {
		  .fzlh(20,24)
		}
		```

		```scss
		// Sass.scss
		my-target {
		  @include fzlh(20,24)
		}
		```

	- Setting font size to 20px:

		```less
		// LESS
		my-target {
		  .fz(20)
		}
		```

		```scss
		// Sass.scss
		my-target {
		  @include fz(20)
		}
		```

	- Setting line spacing to double-spaced:

		```less
		// LESS
		my-target {
		  .lh(2)
		}
		```

		```scss
		// Sass.scss
		my-target {
		  @include lh(2)
		}
		```
