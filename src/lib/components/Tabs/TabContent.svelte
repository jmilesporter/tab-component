<script>
	export let key;
	import { getContext } from 'svelte';
	const store = getContext('activeTabKey');
</script>

{#if $store === key}
	<slot />
{/if}
