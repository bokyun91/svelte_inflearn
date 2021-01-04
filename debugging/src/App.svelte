<script>
	let h1 = '<h1>Hello Heropy</h1>'

	let name = 'Heropy'
	let index = 0
</script>

<!-- @html string -> html 코드처럼 사용 -->
{@html h1}

{@debug index, name}
<h1 on:click={() => {index += 1}}>Hello {name}!</h1>