<script>
  import Card from '$lib/Card.svelte';
  import Canvas from './Canvas.svelte';

  let title;
  let cardType;
  let rules;
  let mana;
  let power;
  let image;
</script>

<div class="wrapper">
  <form>
    <h2> Card Text </h2>
    <label>
      Title:
      <input bind:value={title} />
    </label>
    <label>
      Card Type:
      <input bind:value={cardType} />
    </label>
    <label>
      Rules:
      <textarea bind:value={rules} />
    </label>
    <label>
      Mana:
      <input bind:value={mana} />
    </label>
    <label>
      Power:
      <input bind:value={power} />
    </label>
  </form>
  <div>
    <h2> Card Art </h2>
  <Canvas bind:image />
  </div>
  <Card {title} {cardType} {rules} {mana} {power} {image} />
</div>

<style>
  .wrapper {
    display: flex;
    gap: 10px;
  }

  label {
    display: block;
  }
</style>
