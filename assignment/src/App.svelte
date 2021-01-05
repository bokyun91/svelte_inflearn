<script>
	let name = 'Heropy'
	let fruits = ['Apple', 'Banana', 'Cherry']

	function assign() {
		name = 'Neo'
		fruits.push('Orange')
	}
</script>

<button on:click={assign}>Assign!</button>

<h2>name: {name}</h2>
<h2>fruits: {fruits}</h2>