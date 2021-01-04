<script>
	import Someting from './Someting.svelte'
	let toggle = false
</script>

<button on:click={() => {toggle = !toggle}}>
	Toggle
</button>

{#if toggle}
	<Someting />
{/if}