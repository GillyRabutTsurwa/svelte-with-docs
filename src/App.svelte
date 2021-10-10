<script>
  let title = "Reactivity";
  let subtitle = "Statements";

  const topicPrependText = "reactive-statements";
  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;

  let count = 0;

  function incrementCount() {
    count += 1;
  }

  // ============== NEW: Examples of Reactive Statements ==============
  $: squared = Math.pow(count, 2);

  $: console.log(`The count is ${count}`);

  $: {
    console.log(`Le compte c'est ${count}`);
    console.log(`J'ai dit que le compte c'est ${count}`);
  }

  $: {
    if (squared >= 100) {
      console.warn("Yo, cool down the pace");
    }
  }
  // ===================================================================
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">
      We're not limited to declaring reactive values — we can also run arbitrary statements reactively. For example, we can log the value of count
      whenever it changes.
    </p>
    <p>We can even do things like easily group statements together with a block and write if statements within (Consult Javascript Code)</p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink} target="_blank">Link to Docs</a>
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
