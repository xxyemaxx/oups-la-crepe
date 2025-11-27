<script lang="ts">
	import Header from "$lib/components/Header.svelte";
	import Footer from "$lib/components/Footer.svelte"; // La importación de favicon fue eliminada para resolver el error de ruta.
	// import favicon from "$lib/assets/favicon.svg";
	let { children } = $props();
</script>

<svelte:head>
	<title>Oups la crêpe - La auténtica crepa francesa</title>
</svelte:head>

<Header />

<main>
	{@render children()}
</main>

<Footer />

<style>
	:global(html),
	:global(body) {
		scroll-behavior: smooth;
	}

	:global(body) {
		font-family: "Montserrat", sans-serif;
		background-color: #f8f4ec; /* ¡ACTUALIZADO: Fondo Crema del logo! */
		color: #222222; /* ¡ACTUALIZADO: Texto oscuro del logo! */
		margin: 0;
		padding-top: 60px;
	}

	main {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 20px 0;
		min-height: calc(100vh - 100px);
	}

	:global(h1),
	:global(h2) {
		font-family: "Playfair Display", serif;
		text-transform: uppercase;
		color: #5a3f1f; /* ¡ACTUALIZADO: Un marrón oscuro para títulos, armoniza con el logo! */
	}

	:global(section[id]) {
		scroll-margin-top: 80px;
	}
</style>
