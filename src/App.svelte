<script>
	import Router from "svelte-spa-router";
	import Tailwindcss from "./Tailwindcss.svelte";

	import Footer from "./components/Footer.svelte";
	import Header from "./components/Header.svelte";
	import About from "./routes/About.svelte";
	import Contact from "./routes/Contact.svelte";
	import Home from "./routes/Home.svelte";
	import NotFound from "./routes/NotFound.svelte";
	import Works from "./routes/Works.svelte";
</script>

<Tailwindcss />
<main>
	<Header />
	<Router
		routes={{
			"/": Home,
			"/about": About,
			"/works": Works,
			"/contact": Contact,
			"*": NotFound,
		}}
	/>
	<Footer />
</main>

<style>
	main {
		padding: 0;
		margin: 0;
		min-width: 320px;
		min-height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
	}
</style>
