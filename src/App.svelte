<script>
  let count = $state(0);
  let miliseconds = $state(1000);

  $effect(() => {
    // This will be re-created whenever `miliseconds` changes
    const interval = setInterval(() => {
      count += 1;
    }, miliseconds);

    return () => {
      /**
       * if a teardown function is provided, it will run
       * a) immediately before the effect re-runs
       * b) when the component is destroyed
       */
      clearInterval(interval);
    }
  })
</script>

<h1>{count}</h1>

<button onclick={() => miliseconds *= 2}>slower</button>
<button onclick={() => miliseconds /= 2}>faster</button>