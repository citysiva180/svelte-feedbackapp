<script>
  let firstName = "siva";
  let lastName = "Rajan";
  //   let name = "Siva";
  let color = "purple";
  $: name = firstName + " " + lastName;
  let showText = false;

  let users = [
    {
      id: 1,
      name: "Jeff",
    },
    {
      id: 2,
      name: "Brad",
    },
    {
      id: 3,
      name: "Harry",
    },
  ];

  const toggle = () => {
    color = color === "orange" ? "teal" : "orange";
    showText = !showText;
    users = [...users, { id: 4, name: "Jen" }];
  };
</script>

<main>
  <h1 style="color:{color}">Hello {name}!</h1>
  {#if showText}
    <p>
      Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
      how to build Svelte apps.
    </p>
  {:else}
    <p>Text is hidden, click the button to reveal it</p>
  {/if}
  <button on:click={toggle}>Click Me</button>
  {#each users as user (user.id)}
    <h3>{user.id}: {user.name}</h3>
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #0daf79;
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
