<script>
	import favicon from '$lib/assets/favicon.svg';

	import "$lib/styles/reset.css";
	import "$lib/styles/tokens.css";
	import "$lib/styles/global.css";

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	 <!--Inter Font-->
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous">
	<link href="https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
</svelte:head>

{@render children()}
