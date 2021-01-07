<script>
	import { tick } from 'svelte'
	let count = 0
	let double = 0 

	$: {
		double = count * 2
		console.log('double!')
	}
	
	async function assign() {
		count += 1
		console.time('timer')
		await tick()
		console.timeEnd('timer')
		console.log(double)
	}
</script>

<button on:click={assign}>Assign!</button>
<h2>{count}</h2>
<h2>{double}</h2>