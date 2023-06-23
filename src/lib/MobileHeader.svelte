<script>
	import { slide } from 'svelte/transition'
	import Hamburger from './Hamburger.svelte'
	export let logo = 'My Fun Science'
	let isOpen = false
	let innerWidth

	const toggleMenu = () => isOpen = !isOpen
	const closeMenu = () => isOpen = false

</script>

<svelte:window bind:innerWidth />

<header class="bg-accent">
	<div class="inner">		
		<div class="top">
		<div class="logo">
			<a href="/">{@html logo}</a>
			<div class="trigger" on:click={toggleMenu} on:keypress>
				{#if isOpen}
				<Close />
				{:else}
				<Hamburger />
				{/if}
			</div>
		</div>
			{#if isOpen}
		<nav transition:slide>
			<ul>
				<li><a on:click={closeMenu} href="/">Home</a></li>
				<li><a on:click={closeMenu} href="/about">About</a></li>
                <li><a on:click={closeMenu} href="/gallery">Gallery</a></li>
				<li><a on:click={closeMenu} href="/contact">Contact</a></li>
			</ul>
		</nav>
		{/if}
	</div>
</header>

<style>

	div {
		flex-wrap: wrap;
		justify-content: space-between;
		align-items: center;
		gap: var(--size);
	}

	.top{
		display: flex;
		justify-content: space-between;
	}
	
	.logo {
		font-size: 2rem;
		font-weight: bold;
	}
		
	ul {
		min-height: 100dvh;
		display: flex;
		flex-direction: column;
		gap: var(--size);
		padding-black-start: var(--size);
		font-size: var(--size);
		list-style: none;
	}
	

</style>