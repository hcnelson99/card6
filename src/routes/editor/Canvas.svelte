<script>
  import { onMount } from 'svelte';
  import LineWidthButtons from './LineWidthButtons.svelte';

  export let image;

  let canvas;
  let ctx;
  let pos;

  let lineWidth = 2;


  function getPos(e) {
    let rect = canvas.getBoundingClientRect();
    return {
      x: e.clientX - rect.left,
      y: e.clientY - rect.top
    };
  }

  function setPos(e) {
    pos = getPos(e);
  }

  function draw(e) {
    if (e.buttons !== 1) return;

    ctx.beginPath();
    ctx.lineWidth = lineWidth;
    ctx.lineCap = 'round';
    ctx.strokeStyle = 'black';
    ctx.moveTo(pos.x, pos.y);
    setPos(e);
    ctx.lineTo(pos.x, pos.y);
    ctx.stroke();
    ctx.closePath();
  }

  function save() {
    image = canvas.toDataURL('image/png');
  }

  onMount(() => {
    ctx = canvas.getContext('2d');

    canvas.addEventListener('mousedown', setPos);
    canvas.addEventListener('mouseenter', setPos);
    canvas.addEventListener('mousemove', draw);
    canvas.addEventListener('mouseup', save);
    canvas.addEventListener('mouseleave', save);
  });
</script>

<div class=wrapper>
  <canvas bind:this={canvas} width="246" height="180" />
  <LineWidthButtons bind:lineWidth />
</div>

<style>
  canvas {
    width: 246px;
    height: 180px;
    border: 2px solid black;
  }

  .wrapper {
    display: flex;
    flex-direction: column;
  }
</style>
