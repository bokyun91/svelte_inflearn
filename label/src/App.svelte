<script>
	// Svelte가 아닌, JavaScript 문법입니다!

	loop1:
	for (let i = 1; i < 4; i += 1) {
		loop2:
		for (let k = 1; k < 4; k += 1){
			if (i === 2) {
				break loop2
			}
			console.log(`${i}-${k}`)
		}
		console.log('---------')
	}

	heropy: {
		console.log('a')
		break heropy
		console.log('b')
	}

	// Svelte 반응성 구문!
	let count = 0
	$: {
		console.log(count)
	}
</script>