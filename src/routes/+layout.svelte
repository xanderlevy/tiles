<script>
	import '../app.css';
	let { children } = $props();
</script>


<div class="w-full h-full flex items-center justify-center flex-col p-5">
{@render children()}
</div>
