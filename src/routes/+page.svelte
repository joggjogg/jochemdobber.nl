<script lang="ts">
	import Typewriter from './Typewriter.svelte';
	import LayeredWaves from './layered-waves-haikei-3.svg';
	import Paris2024 from './relay_team.jpeg';
	import Nationals from './nationals.jpeg';
	import Beach from './beach.jpeg';

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
			<button class="call-to-action" type="submit">Send</button>
		</form>
	</div>

	<div class="image">
		<img src="hero.png" alt="Jochem Dobber relay" />
	</div>
</section>

<div class="divider"><img src={LayeredWaves} alt="Layeredwaves" /></div>

<section class="cards">
	<div class="card hvr-grow">
		<img src={Paris2024} alt="Paris 2024" />
		<div class="description">
			<h2>Paris 2024</h2>
			<p>This will be my second Olympics. Check out my mission for Paris 2024.</p>
			<button class="call-to-action">Bekijk</button>
		</div>
	</div>
	<div class="card hvr-grow">
		<img src={Nationals} alt="National Championships 2022" />
		<div class="description">
			<h2>Become a sponsor</h2>
			<p>Want to become part of my team? 🤙</p>
			<button class="call-to-action">Bekijk</button>
		</div>
	</div>
	<div class="card hvr-grow">
		<img src={Beach} alt="Beach" />
		<div class="description">
			<h2>Latest blog</h2>
			<p>Check out my latest blog!</p>
			<button class="call-to-action">Bekijk</button>
		</div>
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
	}

	input {
		width: 100%;
		border: none;
		border-radius: 10px;
		padding: 0.5rem 1rem;
		margin-right: 0.5rem;
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
		box-sizing: border-box;
		background-color: var(--secondary-color);
		padding: var(--column-margin-vertical) var(--column-margin-horizontal);
		display: flex;
		flex-direction: column;
		gap: 4rem;
	}

	.card {
		position: relative;
		width: 100%;
		border-radius: 10px;
		background-color: var(--pure-white);
		display: flex;
		flex-direction: column;
		filter: drop-shadow(0 30px 45px rgba(22, 22, 22, 15%));

		will-change: filter;
		vertical-align: middle;
		-webkit-transform: perspective(1px) translateZ(0);
		transform: perspective(1px) translateZ(0);
		-webkit-transition-duration: 0.3s;
		transition-duration: 0.3s;
		-webkit-transition-property: transform;
		transition-property: transform;
	}

	.card:hover, .card:focus, .card:active {
		-webkit-transform: scale(1.05);
		transform: scale(1.05);
		filter: drop-shadow(0 30px 45px rgba(22, 22, 22, 15%));
	}

	.card img {
		height: 200px;
		object-fit: cover;
		border-top-left-radius: inherit;
		border-top-right-radius: inherit;
	}

	.card .description {
		box-sizing: border-box;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-content: center;
		padding: 1rem;
		bottom: 0;
		width: 100%;
		z-index: 10;
		font-weight: 500;
		color: var(--pure-white);
	}

	.card .description h2 {
		margin-bottom: 0;
		margin-top: 0;
	}

	.card .description p {
		width: 100%;
	}
</style>
