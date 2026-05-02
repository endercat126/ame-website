<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.png';
    import Background from "$lib/Background.svelte";
    import Navigation from "$lib/Navigation.svelte";
    import Ame from "$lib/Ame.svelte";

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<main class="min-h-screen max-w-screen flex flex-col">
    <Background>
        <div class="flex flex-col h-full min-h-full">
            <div class="flex gap-8 h-full">
                <div class="flex flex-col gap-8 items-center h-full ">
                    <Navigation></Navigation>
                    <div class="mt-auto">
                        <Ame></Ame>
                    </div>
                </div>
                {@render children()}
            </div>
            <div id="footer" class="flex gap-2 w-full m-4">
            </div>
        </div>
    </Background>
</main>

<style lang="scss">
    main {
      cursor: url("/assets/cursor.png"), auto;
    }
</style>
