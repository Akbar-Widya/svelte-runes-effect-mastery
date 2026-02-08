<script>
  let state = $state({ value: 0 });
  let derived = $derived({ value: state.value * 2 });

  // this will run once, because `state` is never reassigned
  // open web console to see the log
  $effect(() => {
    state;
    console.log("This runs once on mount");
  })

  // this will run whenever `state.value` changes
  $effect(() => {
    state.value;
    console.log("State value changed:", state.value);
  })

  // and so will this, because `derived` is a new object each time
  $effect(() => {
    derived;
    console.log("Derived changed:", derived.value);
  })
</script>

<button onclick={() => state.value += 1}>
  {state.value}
</button>

<p>{state.value} doubled is {derived.value}.</p>