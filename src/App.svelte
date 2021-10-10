<script>
  let title = "Reactivity";
  let subtitle = "Declarations";

  const topicPrependText = "reactive-declarations";
  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;

  let count = 0;

  function incrementCount() {
    count += 1;
  }

  /** NEW
   * this is the equivalent to computed properties in Vue (at least how they work)
   * the main difference is the minimal syntaxe. observe:
   */

  $: squared = Math.pow(count, 2);

  /**
   * so as you can see, the value of square gets updated, even though it has nothing to do with the incrementCount()
   * this is because incrementCount() changes the value of count, which squared is dependent on
   * to recap, everytime count gets updated, squared does as well
   */
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">
      Svelte automatically updates the DOM when your component's state changes. Often, some parts of a component's state need to be computed from
      other parts (such as a fullname derived from a firstname and a lastname), and recomputed whenever they change.
    </p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink}>Link to Docs</a>
  </div>
  <hr />
  <div class="code">
    <p>{count} squared is {squared}</p>
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

  .docs__text {
    font-size: 1.5em;
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

  button {
    cursor: pointer;
  }
</style>
