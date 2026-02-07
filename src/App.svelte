<script>
  let size = $state(50);
  let color = $state("#ff3e00");

  let canvas;

  $effect(() => {
    const context = canvas.getContext("2d");
    context.clearRect(0, 0, canvas.width, canvas.height);

    context.fillStyle = color;
    context.fillRect(0, 0, size, size);
  })
</script>

<canvas bind:this={canvas} width="100" height="100"></canvas>