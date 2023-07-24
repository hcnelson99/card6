<script>
  export let lineWidth;
  export let setLineWidth;

  $: border = lineWidth == setLineWidth ? '2px solid black' : null;
</script>

<button style="--border: {border}" on:click={() => lineWidth = setLineWidth}>
  <div style="--setLineWidth: {setLineWidth}px"></div>
</button>

<style>
  button {
    border: var(--border);
  }
  div {
    width: var(--setLineWidth);
    height: var(--setLineWidth);
    border-radius: 50%;
    background-color: black;
  }

</style>
