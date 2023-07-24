<script>
  import ColorButton from './ColorButton.svelte';

  export let strokeStyle;
const colors = 

[
['#000000', '#212121', '#424242', '#5e5e5e', '#797979', '#919191', '#929292', '#a9a9a9', '#c0c0c0', '#d5d5d5', '#eaeaea', '#feffff',],
['#941100', '#935100', '#929000', '#4e8f00', '#008e00', '#008f51', '#009192', '#005392', '#011892', '#521b92', '#942092', '#941651',],
['#ff2600', '#ff9300', '#fefb00', '#8df900', '#00f900', '#00fa92', '#00fcff', '#0096ff', '#0432ff', '#9437ff', '#ff40ff', '#ff2f92',],
['#ff7d78', '#ffd478', '#fefc78', '#d4fb78', '#72fa78', '#72fcd5', '#73fdff', '#75d5ff', '#7980ff', '#d783ff', '#ff84ff', '#ff89d8',],
];

</script>


<div class=wrapper>
  {#each colors as color}
    <div class=row>
      {#each color as c}
        <ColorButton bind:color={strokeStyle} setColor={c}/>
      {/each}
    </div>
  {/each}
</div>

<style>
  .wrapper {
    display: flex;
    flex-direction: column;
  }

  .row {
    display: flex;
  }
</style>

