<script lang="ts">
	import Typewriter from './Typewriter.svelte';
	import LayeredWaves from './layered-waves-haikei-3.svg';
	import Paris2024 from './danvernonnbmunichday1-101.jpeg';
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
			<button type="submit" />
		</form>
	</div>

	<div class="image">
		<img src="hero.png" alt="Jochem Dobber relay" />
	</div>
</section>

<div class="divider"><img src={LayeredWaves} alt="Layeredwaves" /></div>

<section class="cards">
	<div class="card">
		<img src={Paris2024} alt="Paris 2024" />
		<div class="description">Parijs 2024</div>
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
		justify-content: space-between;
		gap: 10px;
	}

	input {
		width: 150px;
		border: none;
		border-radius: 10px;
		padding: 0.5rem 1rem;
	}

	button {
		flex-grow: 1;
		width: fit-content;
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

	.image img {
		position: relative;
		height: 100%;
		object-fit: fill;
		left: 30%;
		transform: translateX(-50%);
		mask-image: linear-gradient(to bottom, black, transparent);
		-webkit-mask-image: llinear-gradient(to bottom, black, transparent);
	}

	.divider {
		width: 100%;
		height: 200px;
		overflow-x: hidden;
		overflow-y: hidden;
	}

	.cards {
		width: 100%;
		height: 500px;
		box-sizing: border-box;
		background-color: var(--secondary-color);
		padding: var(--column-margin-vertical) var(--column-margin-horizontal);
		display: flex;
		flex-direction: column;
	}

	.card {
		position: relative;
		width: 100%;
		border-radius: 10px;
		background-color: var(--pure-white);
		height: 200px;
		display: flex;
		flex-direction: column;
		justify-content: flex-end;
		overflow: hidden;
	}

	.card img {
		height: 100%;
		object-fit: cover;
		object-position: 0 -1%;
	}

	.card .description {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		background-color: var(--primary-color);
		padding: 1rem 1.5rem;
		width: 100%;
		z-index: 1;
		font-weight: 500;
	}
</style>
