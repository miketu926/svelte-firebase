<script>
  import About from "./About.svelte";
  import AddingNumbers from "./AddingNumbers.svelte";
  import Logic from "./Logic.svelte";
  export let name;

  let count = 0;

  // to have a 'reactive' declaration, use $: as a prefix to declare variables;

  $: doubled = count * 2;

  // reactive block notation:
  $: {
    console.log(`doubled is: ${doubled}`);
    console.log(`will this console run as well?`);
    console.log("fact: everything in a reactive block will render");
  }

  // reactive JS notation
  $: if (count > 3) {
    console.log(`count is now greater than 3 by this JS notation`);
  }

  // handler function passes through on:click prop
  const handleClick = () => {
    count++;
  };

  let line1 = "This about prop is being rendered in the About component";
  let line2 =
    "Another About component with a differnet prop state. Should use export to expect a prop within the component";
  let line3 =
    "One interesting thing about Svelte is that the stylings within the component is contained - meaning the styling outside of the encapuslated component will not leak into it's children components";
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name}!</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <About about={line1} />
  <About about={line2} />
  <About about={line3} />

  <div>--------------------</div>

  <div>Reactivity: variables</div>
  <button on:click={handleClick}>Clicked {count} doubled is {doubled}</button>
  <AddingNumbers startingNumber={5} />

  <div>--------------------</div>

  <div>Logic</div>
  <Logic />

</main>
