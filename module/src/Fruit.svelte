<script context="module">
  export let count = 0
  console.log('Module context!')
</script>

<script>
  export let fruit
  console.log('Each component init!')
</script>

<div on:click={() => {
  count += 1
  console.log(count)
}}>
  {fruit}({count})
</div>