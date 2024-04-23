<script>
	import reset from '$lib/reset.css?raw';

	let crst = reset;
	let enabled = false;

	let toggle = () => (enabled = !enabled);
	$: action = enabled ? 'disable' : 'enable';
</script>

<svelte:head>
	<title>CSRT: CSS Reset</title>

	<meta name="description" content="CSRT: CSS Reset" />

	<!-- trick to conditionally apply css -->
	{#if enabled}
		<style contenteditable bind:textContent={crst}></style>
	{/if}
</svelte:head>

<h1>🥐 crst: css reset</h1>
<p>
	<code>crst</code> (pronounced: croissant) obliterates default browser css styles in order to start
	with a (consistent) clean sheet when writing your own styles.
</p>

<p>It's inspired by many similar projects:</p>
<ul>
	<li><a href="https://necolas.github.io/normalize.css/">Normalize.css</a></li>
	<li><a href="https://github.com/sindresorhus/modern-normalize">Modern Normalize</a></li>
	<li><a href="https://elad2412.github.io/the-new-css-reset/">The New CSS Reset</a></li>
</ul>

<p>
	⚠️ It's imperative to use this as a starting point for designing your own styles, unless you
	really hate your users.
</p>

<p>Click on the button below to {action} crst:</p>

<button on:click={toggle}>
	{action} crst
</button>
