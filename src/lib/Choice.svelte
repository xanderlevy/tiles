<script>
	let { i, tiles = $bindable() } = $props();
</script>

<div class="opacity-0 hover:opacity-100 transition w-full h-full flex items-center justify-center gap-1">
	<button
		class="h-5 w-5 rounded-full bg-green-400 transition hover:scale-110"
		onclick={() => {
			tiles[i].color = 'green';
		}}
	></button>
	<button
		class="h-5 w-5 rounded-full bg-orange-400 transition hover:scale-110"
		onclick={() => {
			tiles[i].color = 'orange';
		}}
	></button>
	<button
		class="h-5 w-5 rounded-full bg-purple-400 transition hover:scale-110"
		onclick={() => {
			tiles[i].color = 'purple';
		}}
	></button>
</div>
