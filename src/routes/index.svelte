<script>
	import Tab from '../lib/components/Tabs/Tab.svelte';
	import TabContent from '../lib/components/Tabs/TabContent.svelte';
	import TabGroup from '../lib/components/Tabs/TabGroup.svelte';
	const tabs = [
		['One', 'Content for tab one.'],
		['Two', 'Content for tab two.'],
		['Three', 'Content for tab three.']
	];
</script>

<main>
	<div class="component">
		<TabGroup active={0}>
			<span slot="tabs">
				{#each tabs as [title, body], index}
					<Tab key={index}>{title}</Tab>
				{/each}
			</span>
			{#each tabs as [title, body], index}
				<TabContent key={index}>{body}</TabContent>
			{/each}
		</TabGroup>
	</div>
</main>

<style>
	.component {
		display: grid;
		place-items: center;
		margin: 3em;
	}
</style>
