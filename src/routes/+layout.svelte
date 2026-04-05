<script>
	import favicon from '$lib/assets/favicon.ico';

	let { children } = $props();
</script>

<svelte:head>
	<title>Medical Scenario Generator</title>
	<link rel="icon" href={favicon} />
	<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
	<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
	<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
	<link rel="manifest" href="/site.webmanifest">
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

  /* Mobile */
  @media (max-width: 768px) {
    h1 {
      font-size: 1.4em;
    }

	header {
	  justify-content: center;
	}


  }


</style>

{@render children()}
