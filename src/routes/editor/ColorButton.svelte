<script>
  export let color;
  export let setColor;

  $: border = color == setColor ? '2px solid black' : null;
</script>

<button 
  style="--border: {border}; --setColor: {setColor}" 
  on:click={() => color = setColor}>
</button>

<style>
  button {
    border: var(--border);
    background-color: var(--setColor);
    width: 16px;
    height: 16px;
  }

</style>
