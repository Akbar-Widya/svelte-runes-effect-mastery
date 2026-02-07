<script>
  let size = $state(50);
  let color = $state("#ff3e00");

  let canvas;

  $effect(() => {
    const context = canvas.getContext("2d");
    context.clearRect(0, 0, canvas.width, canvas.height);

    // this will re-run whenever `color` or `size` change
    context.fillStyle = color;

    setTimeout(() => {
      // but not when `size` changes
      context.fillRect(0, 0, size, size);
    }, 0);
  });
</script>

<canvas bind:this={canvas} width="100" height="100"></canvas>
<input bind:value={color} onchange={() => color = color}>
<input type="number" bind:value={size} min="10" max="500" step="20">