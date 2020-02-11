<script>
  let user = { loggedIn: false };

  const toggle = () => {
    user.loggedIn = !user.loggedIn;
  };
</script>

{#if user.loggedIn}
  <button on:click={toggle}>Log out</button>
{:else}
  <button on:click={toggle}>Log in</button>
{/if}

<div>
  <div>HTML Template is wrapped in curly braces</div>
  <div>if blocks #if -> :else if -> :else -> /if</div>
  <div>each blocks #each lists as list, idx -> /each</div>
</div>
