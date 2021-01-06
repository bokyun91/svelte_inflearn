<script>
	let name = 'Heropy'
	let fruits = ['Apple', 'Banana', 'Cherry']
	let user = {
		name : 'Heropy', 
		depth : {
			a : 'b'
		},
		numbers: [1, 2]
	}

	let numbers = user.numbers
	let hello = 'world'

	function assign() {
		name = 'Neo'
		//fruits.push('Orange')
		//fruits = fruits
		fruits = [...fruits, 'Orange']
		user.name = 'Neo'
		user.depth.a = 'c'
		user.numbers.push(3)
		numbers = numbers
	}
</script>

<button on:click={assign}>Assign!</button>

<h2>name: {name}</h2>
<h2>fruits: {fruits}</h2>
<h2>user name: {user.name}</h2>
<h2>user depth a: {user.depth.a}</h2>
<h2>user numbers: {user.numbers}</h2>
<h2>numbers: {numbers}</h2>
<h2>{hello}</h2>