<script>
import Choice from "../lib/Choice.svelte";

	let x = $state(0);
	
	let tiles1 = $state([
		{
			color: 'blue',
			type: 'tile'
		},
		{
			color: 'none',
			type: 'choice'
		},
		{
			color: 'none',
			type: 'choice'
		},
		{
			color: 'red',
			type: 'tile'
		}
	]);
	let tiles2 = $state([
		{
			color: 'none',
			type: 'choice'
		},
		{
			color: 'pink',
			type: 'tile'
		},
		{
			color: 'none',
			type: 'choice'
		},

		{
			color: 'none',
			type: 'choice'
		}
	]);

	let tiles3 = $state([
		{
			color: 'red',
			type: 'tile'
		},
		{
			color: 'blue',
			type: 'tile'
		},
		{
			color: 'none',
			type: 'choice'
		},
		{
			color: 'pink',
			type: 'tile'
		}
	]);
</script>

<div class="flex h-full w-full flex-col items-center justify-center">
	<div class="flex">
		{#each tiles1 as a, i}
			{#if i === 0}
				<div
					class="{a.color} flex h-20 w-20 items-center justify-center gap-1 border-2 border-b-0 border-black"
				>
					{#if a.type === 'choice'}
						<Choice bind:tiles={tiles1} {i} />
					{/if}
				</div>
			{:else}
				<div
					class="{a.color} flex h-20 w-20 items-center justify-center gap-1 border-2 border-b-0 border-l-0 border-black"
				>
					{#if a.type === 'choice'}
						<Choice bind:tiles={tiles1} {i} />
					{/if}
				</div>
			{/if}
		{/each}
	</div>
	<div class="flex">
		{#each tiles2 as a, i}
			{#if i === 0}
				<div
					class="{a.color} flex h-20 w-20 items-center justify-center gap-1 border-2 border-b-0 border-black"
				>
					{#if a.type === 'choice'}

						<Choice bind:tiles={tiles2} {i} />
					{/if}
				</div>
			{:else}
				<div
					class="{a.color} flex h-20 w-20 items-center justify-center gap-1 border-2 border-b-0 border-l-0 border-black"
				>
					{#if a.type === 'choice'}
						<Choice bind:tiles={tiles2} {i} />
					{/if}
				</div>
			{/if}
		{/each}
	</div>
	<div class="flex">
		{#each tiles3 as a, i}
			{#if i === 0}
				<div
					class="{a.color} flex h-20 w-20 items-center justify-center gap-1 border-2 border-black"
				>
					{#if a.type === 'choice'}
						<Choice bind:tiles={tiles3} {i} />
					{/if}
				</div>
			{:else}
				<div
					class="{a.color} flex h-20 w-20 items-center justify-center gap-1 border-2 border-l-0 border-black"
				>
					{#if a.type === 'choice'}
						<Choice bind:tiles={tiles3} {i} />
					{/if}
				</div>
			{/if}
		{/each}
	</div>
</div>
<div class="flex items-center gap-10">
	<div class="flex">
		<div class="green h-5 w-5 border-2 border-black"></div>
		<div class="blue h-5 w-5 border-2 border-l-0 border-r-0 border-black"></div>
		<div class="green h-5 w-5 border-2 border-black"></div>
	</div>
	<div class="flex flex-col">
		<div class="orange h-5 w-5 border-2 border-black"></div>
		<div class="red h-5 w-5 border-2 border-b-0 border-t-0 border-black"></div>
		<div class="orange h-5 w-5 border-2 border-black"></div>
	</div>
	<div class="relative flex flex-col">
		<div class="purple absolute -left-5 -top-5 h-5 w-5 border-2 border-black"></div>
		<div class="pink h-5 w-5 border-2 border-black"></div>
		<div class="purple absolute -right-5 top-5 h-5 w-5 border-2 border-black"></div>
	</div>
</div>

<style>
	.blue {
		@apply bg-blue-400;
	}
	.red {
		@apply bg-red-400;
	}
	.pink {
		@apply bg-pink-400;
	}
	.green {
		@apply bg-green-200;
	}
	.orange {
		@apply bg-orange-200;
	}

	.purple {
		@apply bg-purple-200;
	}
</style>
