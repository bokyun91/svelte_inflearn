<script>
	import { tick } from "svelte";

	let name = 'world'

	// svelte는 기본적으로 모두 실행된 다음 화면 갱신. 그래서 Hello Heropy가 아닌 Hello World가 콘솔에 출력
	async function handler() {
		name = 'Heropy'
		await tick() // tick은 비동기. await 붙이고 function에 async
		const h1 = document.querySelector('h1')
		console.log(h1.innerText)
	}
</script>

<h1 on:click={handler}>Hello {name}!</h1>