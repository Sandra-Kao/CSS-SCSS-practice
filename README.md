# CSS-SCSS-practice
Please see codepen: https://codepen.io/K-SY/pen/abpewVb


```scss 
* {
	padding: 0;
	margin: 0;
}

html {
	font-size: 100%;
}
.title {
	padding: 1rem 2rem;
	font-size: 2rem;
	text-align: center;
}

$color-white: #fff;
$color-defalt: #c8d9e7;
$color-secend: #7107a1;
$color-third: #420347;
$color-fourth: #ff6600;
$color-fiveth: #ff1100;
@mixin style-link($custom-font-color) {
	text-transform: uppercase;
	text-decoration: none;
	margin-left: 1rem;
	padding: 0.5rem 1rem;
	color: $custom-font-color;
	&:hover {
		text-decoration: underline;
		color: $color-third;
	}
}

%link-pleaseholder {
	@include style-link($color-white);
	border-radius: 100px;
	text-align: center;
}

.clearfix::after {
	content: "";
	display: table;
	clear: both;
}

@function divide($a, $b) {
	@return $a / $b;
}

.navigation {
	margin: 1rem divide(60, 2) * 0.1rem; //30px
	background: $color-defalt;
	font-size: 1rem;
	padding: 1.2rem;
	.navigation__list {
		float: left;
		margin: 0.5rem;
		li {
			list-style: none;
			margin: 0.25rem;
			display: inline-block;
		}
		a {
			@include style-link($color-secend);
		}
	}
	.navigation__buttons {
		float: right;
		margin: 0.5rem;
		.navigation__buttons--main {
			&:link {
				@extend %link-pleaseholder;
				background: $color-fourth;
			}
			&:hover {
				background: darken($color: $color-fourth, $amount: 20%);
			}
		}
		.navigation__buttons--hot {
			&:link {
				@extend %link-pleaseholder;
				background: $color-fiveth;
			}
			&:hover {
				background: lighten($color: $color-fiveth, $amount: 20%);
			}
		}
	}
}
```
