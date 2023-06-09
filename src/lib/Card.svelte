<script>
	export let post
	export let buttonText = "More"
	
	const { featured_image, title, excerpt } = post
</script>

<li class="bg-light">
	<img class="square" src="{featured_image}" alt="placeholder">
	<div>
		<h2>{@html title}</h2>
		<p>{@html excerpt}</p>
		<a class="button" href>{buttonText}</a>
	</div>
</li>

<style>

	div {
		display: grid;
		gap: 1em;
		padding: 1.5em;
	}
</style>