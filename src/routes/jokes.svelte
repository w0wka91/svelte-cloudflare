<script context="module" lang="ts">
	import type { Load } from '@sveltejs/kit';

	export const load: Load = async ({ fetch }) => {
		const response = await fetch('https://v2.jokeapi.dev/joke/Any?type=twopart');
		const data = await response.json();
		return {
			props: {
				setup: data.setup,
				delivery: data.delivery
			}
		};
	};
</script>

<script lang="ts">
	export let setup;
</script>

<h1>{setup}</h1>
