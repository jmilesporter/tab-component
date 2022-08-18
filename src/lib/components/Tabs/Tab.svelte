<script>
	export let key;
	import { getContext } from 'svelte';
	const store = getContext('activeTabKey');
</script>

<div class:active={key === $store} class="tab" on:click={() => ($store = key)} on:hover>
	<slot />
</div>

<style>
	.tab {
		display: inline-block;
		padding: 1em;
		border-bottom: none;
	}
	.tab.active {
		background-color: black;
		color: white;
	}
	.tab:not(.active):hover {
		cursor: pointer;
		color: var(--tab-color-hover-fg, black);
		background-color: var(--tab-color-hover-bg, lightgray);
	}
</style>
