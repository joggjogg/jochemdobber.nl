<script lang="ts">
	import Typewriter from './Typewriter.svelte';

	const titles = ['Olympic Medalist', 'Web Developer', 'Puma Athlete'];
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Jochem Dobber" />
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

<div class="divider"><img src="/vectors/layered-waves-haikei-3.svg" alt="Layeredwaves" /></div>

<section class="cards">
	<div class="card hvr-grow">
		<img src="/images/relay_team.jpeg" alt="Paris 2024" />
		<div class="description">
			<h2>Paris 2024</h2>
			<p>This will be my second Olympics. Check out my mission for Paris 2024.</p>
			<button class="call-to-action">Bekijk</button>
		</div>
	</div>
	<div class="card hvr-grow">
		<img src="/images//nationals.jpeg" alt="National Championships 2022" />
		<div class="description">
			<h2>Become a sponsor</h2>
			<p>Want to become part of my team? 🤙</p>
			<button class="call-to-action">Bekijk</button>
		</div>
	</div>
	<div class="card hvr-grow">
		<img src="/images/beach.jpeg" alt="Beach" />
		<div class="description">
			<h2>Latest blog</h2>
			<p>Check out my latest blog.</p>
			<button class="call-to-action">Bekijk</button>
		</div>
	</div>
</section>

<section class="brands">
	<h2>These brands support me</h2>
	<div class="brands__wrapper">
		<div class="brands__row">
			<div class="brands__item">
				<img class="brands__logo" src="/vectors/puma-logo.svg" alt="Puma" />
			</div>
		</div>

		<div class="brands__row">
			<div class="brands__item">
				<img class="brands__logo" src="/images/coffeeclick.jpg" alt="CoffeeClick" />
			</div>
			<div class="brands__item">
				<img class="brands__logo" src="/images/nedflex.png" alt="Nedflex" />
			</div>
		</div>

		<div class="brands__row">
			<div class="brands__item">
				<img class="brands__logo" src="/vectors/bdo.svg" alt="BDO" />
			</div>
			<div class="brands__item">
				<img class="brands__logo" src="/images/suomi.png" alt="AV Suomi" />
			</div>
			<div class="brands__item">
				<img class="brands__logo" src="/images/rene-kops.png" alt="Rene Kops" />
			</div>
		</div>
	</div>

	<h3>Recovery partner</h3>
	<div class="brands__wrapper">
		<div class="brands__row">
			<div class="brands__item">
				<img class="brands__logo" src="/vectors/amplify.svg" alt="Amplify" />
			</div>
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
		margin: var(--column-margin-vertical) var(--column-margin-horizontal);
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

	.card:hover,
	.card:focus,
	.card:active {
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

	.brands {
		padding: var(--column-margin-vertical) var(--column-margin-horizontal);
		display: flex;
		flex-direction: column;
	}

	.brands h2 {
		text-align: center;
		margin-bottom: 3rem;
	}

	.brands h3 {
		margin-bottom: 3rem;
	}

	.brands__wrapper {
		display: flex;
		flex-direction: column;
		gap: 4rem;
		margin-bottom: 2rem;
	}

	.brands__row {
		display: flex;
		flex: 1;
		flex-wrap: wrap;
		gap: 3rem;
	}

	.brands__item {
		flex: 1;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
	}

	img.brands__logo {
		width: 100%;

	}

	.brands h3 {
		text-align: center;
	}
</style>
