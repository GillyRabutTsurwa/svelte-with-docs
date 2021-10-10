<script>
  let title = "Reactivity";
  let subtitle = "Assignments";

  const topicPrependText = "reactive-assignments";
  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;

  let count = 0;

  function incrementCount() {
    count += 1;
  }
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">
      At the heart of Svelte is a powerful system of reactivity for keeping the DOM in sync with your application state — for example, in response to
      an event. To demonstrate it, we first need to wire up an event handler (we will go through event handlers later)
    </p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink}>Link to Docs</a>
  </div>
  <hr />
  <div class="code">
    <p>{count}</p>
    <button on:click={incrementCount}>Clicked {count === 1 ? "time" : "times"}</button>
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
    height: 100vh;
    overflow: hidden;
    background-color: var(--background-primary);
  }

  h1,
  h2 {
    text-transform: uppercase;
  }

  h1 {
    font-size: 4em;
    font-weight: 100;
  }
  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  .links {
    margin: 2.5em 0;
  }

  hr {
    width: 50%;
  }

  p {
    color: bisque;
  }
</style>
