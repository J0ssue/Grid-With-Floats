<style lang="scss" scoped>
	@mixin clearfix {
		&::after {
			content: "";
			display: table;
			clear: both;
		}
	}

	$grid-width: 114rem;
	$gutter-vertical: 8rem;
	$gutter-horizontal: 6rem;

	.row {
		max-width: $grid-width;
		background-color: #eee;
		margin: 0 auto;

		&:not(:last-child) {
			margin-bottom: $gutter-vertical;
		}

		@include clearfix;

		// select all divs that start with 'col-'
		[class^="col-"] {
			background-color: orangered;
			float: left;

			&:not(:last-child) {
				margin-right: $gutter-horizontal;
			}
		}

		.col-1-of-2 {
			width: calc((100% - #{$gutter-horizontal}) / 2);
		}

		.col-1-of-3 {
			width: calc((100% - 2 * #{$gutter-horizontal}) / 3);
		}

		.col-2-of-3 {
			width: calc(
				2 * ((100% - 2 * #{$gutter-horizontal}) / 3) + #{$gutter-horizontal}
			);
		}

		.col-1-of-4 {
			width: calc((100% - 3 * #{$gutter-horizontal}) / 4);
		}

		.col-2-of-4 {
			width: calc(
				2 * ((100% - 3 * #{$gutter-horizontal}) / 4) + #{$gutter-horizontal}
			);
		}
		.col-3-of-4 {
			width: calc(
				3 * ((100% - 3 * #{$gutter-horizontal}) / 4) + #{$gutter-horizontal} * 2
			);
		}
	}
</style>

<template>
	<div id="app">
		<section class="grid-te">
			<div class="row">
				<div class="col-1-of-2">col 1 of 2</div>
				<div class="col-1-of-2">col 1 of 2</div>
			</div>
			<div class="row">
				<div class="col-1-of-3">col 1 of 3</div>
				<div class="col-1-of-3">col 1 of 3</div>
				<div class="col-1-of-3">col 1 of 3</div>
			</div>
			<div class="row">
				<div class="col-1-of-3">col 1 of 3</div>
				<div class="col-2-of-3">col 2 of 3</div>
			</div>
			<div class="row">
				<div class="col-1-of-4">col 1 of 4</div>
				<div class="col-1-of-4">col 1 of 4</div>
				<div class="col-1-of-4">col 1 of 4</div>
				<div class="col-1-of-4">col 1 of 4</div>
			</div>
			<div class="row">
				<div class="col-1-of-4">col 1 of 4</div>
				<div class="col-1-of-4">col 1 of 4</div>
				<div class="col-2-of-4">col 2 of 4</div>
			</div>
			<div class="row">
				<div class="col-1-of-4">col 1 of 4</div>
				<div class="col-3-of-4">col 3 of 4</div>
			</div>
		</section>
	</div>
</template>

<script>
	export default {
		name: "app"
	};
</script>

