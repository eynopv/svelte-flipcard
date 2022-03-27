<script>
  import Flipcard from './Flipcard.svelte';
</script>


<style>
  main :global(.flipcard) {
    margin: 0 auto;
  }
</style>

<main>
  <Flipcard>
    <svelte:fragment slot="front">
      <div style="background-color: red"></div>
    </svelte:fragment>

    <svelte:fragment slot="back">
      <div style="bacgrkound-color: green"></div>
    </svelte:fragment>
  </Flipcard>
</main>
