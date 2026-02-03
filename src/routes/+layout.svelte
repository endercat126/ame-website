<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.png';
    import Background from "$lib/Background.svelte";
    import Navigation from "$lib/Navigation.svelte";

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<main class="min-h-screen max-w-screen flex flex-col">
    <Background>
        <Navigation></Navigation>
        {@render children()}
    </Background>
</main>
