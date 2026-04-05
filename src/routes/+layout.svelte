<script>
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Medical Scenario Generator</title>
</svelte:head>

<header>
	<h1>Medical Scenario Generator</h1>
</header>

<style>
    h1 {
	font-size: 3em;
	/* text-align: center; */
	margin: 20px;
  }

  h1 {
	font-family: Arial, Helvetica, sans-serif;
  }

  header {
	display: flex;
	justify-content: left;
	align-items: center;
	color: white;
	background-color: rgb(0, 0, 62);
  }

</style>

{@render children()}
