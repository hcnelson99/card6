<script>
  import LineWidthButton from './LineWidthButton.svelte';

  export let lineWidth;

  const widths = [1, 2, 4, 8, 16, 32 ];
</script>


<div class=wrapper>
  {#each widths as width}
    <LineWidthButton bind:lineWidth setLineWidth={width}/>
  {/each}
</div>

<style>
  .wrapper {
    display: flex;
  }
</style>
