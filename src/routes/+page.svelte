<script lang="ts">
	import Typewriter from './Typewriter.svelte';

	const titles = ['Olympic Medalist', 'Web Developer', 'Puma Athlete'];
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Jochem Dobber website" />
</svelte:head>

<section class="hero">
	<div class="description">
		<h1>
			Hi, my name is Jochem and I'm a<Typewriter
				>{#each titles as title}
					<div class="title">{title}</div>
				{/each}</Typewriter
			>
		</h1>
		<p>Want to follow my adventure? Sign up for my newsletter!</p>
		<form action="">
			<input type="email" name="email" id="email">
			<button type="submit">Sign up</button>
		</form>
	</div>

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

	h1 {
		text-align: left;
	}

	.title {
		color: var(--accent-color);
	}

	.description {
		display: flex;
		flex-direction: column;
	}

	form {
		display: flex;
		flex-direction: row;
		gap: 10px;
	}

	input {
		padding: 15px;
		border: none;
		border-radius: 10px;
	}

	button {
		padding: 15px;
		border: none;
		color: var(--pure-white);
		background-color: var(--accent-color);
		border-radius: 10px;
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
