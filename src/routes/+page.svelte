<script lang="ts">
	import Typewriter from './Typewriter.svelte';

	const titles = ['Olympic Medalist', 'Web Developer', 'Puma Athlete'];
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Jochem Dobber website" />
</svelte:head>

<section class="hero">
	<div class="welcome-text">
		<h1>
			Hi, my name is Jochem and I'm a<Typewriter
				>{#each titles as title}
					<div class="title">{title}</div>
				{/each}</Typewriter
			>
		</h1>
		<p>Want to follow my adventure? Sign up for my newsletter!</p>
		<form action="">
			<input type="email" name="email" id="email" />
			<button type="submit"></button>
		</form>
	</div>

	<div class="image">
		<img src="hero.png" alt="Jochem Dobber relay" />
	</div>
</section>

<style>
	.hero {
		position: relative;
		overflow-x: hidden;
		background-color: var(--primary-color);
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		height: 80vh;
		margin: 0 var(--column-margin-horizontal);
		border-radius: 10px;
		padding: 1rem 0;
	}

	h1 {
		text-align: left;
		font-size: 26px;
		margin-bottom: 0;
	}

	p {
		font-size: 16px;
	}

	.title {
		width: 100%;
		color: var(--pure-white);
		font-size: 26px;
		white-space: nowrap;
	}

	.welcome-text {
		padding: 0 1.5rem;
		display: flex;
		flex-direction: column;
		z-index: 1;
	}

	form {
		width: 100%;
		display: flex;
		flex-direction: row;
	}

	input {
		border: none;
		box-sizing: border-box;
		border-radius: 10px;
		padding: 0.5rem 1rem;
	}

	button {
		border: none;
		color: var(--pure-white);
		background-color: var(--accent-color);
		border-radius: 10px;
	}

	.image {
		position: absolute;
		height: 100%;
		z-index: 0;
	}

	img {
		position: relative;
		height: 100%;
		object-fit: fill;
		left: 30%;
		transform: translateX(-50%);
		mask-image: linear-gradient(to bottom, black, transparent);
		/* -webkit-mask-image: linear-gradient(to bottom, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0.65) 100%); */
	}
</style>
