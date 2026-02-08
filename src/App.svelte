<script>
  import confetti from "canvas-confetti";

  let condition = $state(false);
  let color = $state("#ff3e00");

  $effect(() => {
    // the effect will only re-run again when condition changes.
    if (condition) {
      confetti({ colors: [color] });
    } else {
      confetti();
    }
  });
</script>

<h2>Click the button to switch confetti colors!</h2>
<button onclick={() => condition = !condition}>Change Colors</button>
