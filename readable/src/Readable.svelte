<script>
  import { user } from './store.js'

  console.log(user)
  console.log($user)
</script>

<button on:click={() => {
  $user.name = 'Neo'
}}>
  Click!
</button>
<h2>{$user.name}</h2>
