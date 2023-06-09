<script>
	export let post
	export let buttonText = "Something"
	
	const { featured_image, title, excerpt } = post
</script>

<li>
	<img src="{featured_image}" alt="placeholder">
	<div>
		<h2>{@html title}</h2>
		<p>{@html excerpt}</p>
		<a href>{buttonText}</a>
	</div>
</li>

<style>
	li {
		margin-inline: auto;
		background-color: white;
	}
	
	img {
		display: block;
		width: 100%;
		aspect-ratio: 1;
		object-fit: cover;
	}
	
	h2 {
		line-height: 1.25;
	}
	
	div {
		display: grid;
		gap: 1em;
		padding: 1.5em;
	}
	
	a {
		padding: 1em;
		background-color: tomato;
		color: white;
		text-align: center;
		text-transform: uppercase;
		font-weight: bold;
		letter-spacing: 1px;
		border: none;
		cursor: pointer;
	}
	
	a:hover {
		background-color: transparent;
		color: tomato;
		outline: 0.25em solid tomato;
		text-decoration: none;
	}
</style>