<script>
  // default can be set here if no props are passed down
  export let startingNumber = 1;

  // Svelte's reactivity is triggered by assignments***
  let numbers = [startingNumber];

  const handleAddNumber = () => {
    numbers = [...numbers, numbers[numbers.length - 1] + 1];
  };

  // reactivity as a variable to render
  $: numberString = `${numbers.join(" + ")} = ${numbers.reduce(
    (a, n) => a + n
  )}`;
</script>

<div>
  <button on:click={handleAddNumber}>Add Number</button>
  <div>{numberString}</div>
</div>
