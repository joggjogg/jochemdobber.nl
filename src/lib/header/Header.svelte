<script lang="ts">
	import { page } from '$app/stores';
</script>

<header>
	<nav>
		<ul>
			<li class:active={$page.url.pathname === '/'}><a sveltekit:prefetch href="/">Home</a></li>
			<li class:active={$page.url.pathname === '/blog'}>
				<a sveltekit:prefetch href="/blog">Blog</a>
			</li>
			<li class:active={$page.url.pathname === '/contact'}>
				<a sveltekit:prefetch href="/contact">Contact</a>
			</li>
		</ul>
	</nav>
</header>

<style>
	header {
		position: fixed;
		bottom: 0;
		margin-bottom: -;
		width: 100%;
		box-sizing: border-box;
		/* From https://css.glass */
		background: rgba(255, 255, 255, 0.2);
		border-top-left-radius: 10px;
		border-top-right-radius: 10px;
		box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
		backdrop-filter: blur(5px);
		-webkit-backdrop-filter: blur(5px);
		border: 1px solid rgba(255, 255, 255, 0.3);
		border-bottom: none;
		z-index: 10;
		display: flex;
		justify-content: space-between;
		border-top-left-radius: 10px;
		padding: .5rem 1rem
	}

	nav {
		display: flex;
		width: 100%;
		justify-content: center;
	}

	ul {
		width: 100%;
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: space-between;
		align-items: center;
		list-style: none;
		background-size: contain;
	}

	li {
		position: relative;
		height: 100%;
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		color: var(--heading-color);
		font-weight: 400;
		font-size: 0.8rem;
		text-transform: lowercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--accent-color);
	}

	@media only screen and (min-width: 768px) {
		ul {
			width: 300px;
		}
	}
</style>
