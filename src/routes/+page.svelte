<script lang="ts">
	import Typewriter from './Typewriter.svelte';

	const titles = ['Olympic Medalist', 'Web Developer', 'Puma Athlete'];
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Jochem Dobber website" />
</svelte:head>

<section class="hero">
	<h1>
		Hi, my name is Jochem and I'm a<Typewriter
			>{#each titles as title}
				<div class="title">{title}</div>
			{/each}</Typewriter
		>
	</h1>
	<div class="image">
		<img src="hero.png" alt="Jochem Dobber relay" />
	</div>
</section>

<style>
	.hero {
		background-color: var(--background);
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		height: 80vh;
		margin: 0 4em;
		padding: 4em;
		box-sizing: border-box;
		border-radius: 10px;
	}

	.title {
		color: var(--accent-color)
	}

	h1 {
		flex: 1 0 0;
		text-align: left;
	}

	.image {
		margin-top: -5em;
		margin-bottom: -4em;
		width: 60%;
	}

	img {
		height: 100%;
		object-fit: fill;
	}
</style>
