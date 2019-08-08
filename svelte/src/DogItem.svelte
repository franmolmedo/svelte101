<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let id;
  export let name;
  export let thumbnail;
</script>

<style>
  article {
    cursor: pointer;
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>

<article on:click={() => dispatch('selectitem', { id })}>
  <h1>{name}</h1>
  <img alt={name} src={thumbnail} />
</article>
