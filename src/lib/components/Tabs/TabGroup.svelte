<script>
	export let active;
	import { writable } from 'svelte/store';
	import { setContext } from 'svelte';
	const store = writable(active);
	setContext('activeTabKey', store);
</script>

<div class="tabs">
	<slot name="tabs" />
</div>
<div class="tab-content">
	<slot />
</div>

<style>
	.tabs {
		border-bottom: solid black 2px;
	}
	.tab-content {
		padding: 1em;
	}
</style>
