<script>
    import { afterUpdate, beforeUpdate, onDestroy, onMount } from 'svelte'

    let name = 'Something..'
    let h1

    function moreDot() {
        name += '.'
    }

    // 화면이 바뀌기 전 한번 실행
    beforeUpdate(() => {
        console.log('Before update!')
        console.log(h1 && h1.innterText) 
    })

    // 화면이 바뀐 뒤 한번 실행
    afterUpdate(() => {
        console.log('After update!')
        console.log(h1.innterText)
    })

    onMount(() => {
        console.log("Mounted!")
        // destroy와 같음. 다만 onDestory() 다음 실행. 비동기가 없는 경우에만 가능(async X)
        h1 = document.querySelector('h1')
    })

    onDestroy(() => {
        console.log('Before destory~')
        // destory 직전 실행
        // const h1 = document.querySelector('h1')
        // console.log(h1.innerText)
    })
</script>
<h1 on:click={moreDot}>{name}</h1>