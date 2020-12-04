<script lang="ts">
	import Nav from '../components/Nav.svelte';

	export let segment: string;
</script>

<style>
</style>

<Nav {segment}/>

<main class="min-h-screen">
	<slot></slot>
</main>