<script lang="ts">
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Jochem Dobber personal website" />
</svelte:head>

<section class="hero">
	<h1>Hi, my name is Jochem and I'm an <span>Olympic Medalist</span>.</h1>
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
		flex: 1 0 0;
		text-align: left;
	}

	span {
		color: var(--accent-color);
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
