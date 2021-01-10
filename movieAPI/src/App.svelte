<script>
	import axios from 'axios'

	let apikey = 'e61ff919'
	let title = ''
	//let promise = new Promise((resolve) => {resolve([])})
	let promise = Promise.resolve([])

	function searchMovies() {
		return new Promise(async (resolve, reject) => {
			try {
				const res = await axios.get(`http://www.omdbapi.com/?apikey=${apikey}&s=${title}`)
				resolve(res.data.Search)
			} catch(err) {
				reject(err)
			} finally {
				console.log('Done!')
			}
		})
	}
</script>

<input bind:value={title} />
<button on:click={() => {
	promise = searchMovies()
}}>검색!</button>

{#await promise}
	<p style="color: royalblue">Loading...</p>
{:then movies}
	<ul>
		{#each movies as movie}
			<li>{movie.Title}</li>
		{/each}
	</ul>
{:catch error}
	<p style="color:red;">{error.message}</p>
{/await}

<!--
{#if loading}
	<p style="color: royalblue">Loading...</p>
{:else if movies}
	<ul>
		{#each movies as movie}
			<li>{movie.Title}</li>
		{/each}
	</ul>
{:else if error}
	<p style="color:red;">{error.message}</p>
{/if}
-->