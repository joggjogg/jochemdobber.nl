<script>
	import Typewriter from 'svelte-typewriter';
</script>

<Typewriter mode="loop" interval={80}>
	<slot />
</Typewriter>
