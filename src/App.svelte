<script>
  let title = "Reactivity";
  let subtitle = "Updating Arrays & Objects";

  const topicPrependText = "updating-arrays-and-objects";
  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;

  let numbers = [1, 2, 3, 4];
  let numéros = [1, 2, 3, 4];

  // NOTE: this function is not ideal, as it is redundant. but it works
  function addNumber() {
    numbers.push(numbers.length + 1);
    numbers = numbers;
  }

  //NOTE: cette fonction est beaucoup mieux, et fait la même action
  function addNumberBetter() {
    numéros = [...numéros, numéros.length + 1];
  }

  $: sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
  $: somme = numéros.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">
      Because Svelte's reactivity is triggered by assignments, using array methods like push and splice won't automatically cause updates. For
      example, clicking the button doesn't do anything.
    </p>
    <p class="docs__text">You can use similar patterns to replace pop, shift, unshift and splice.</p>
    <p>If you still don't understand, come back to this branch and play around</p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink} target="_blank">Link to Docs</a>
  </div>
  <hr />
  <div class="code">
    <div class="example1">
      <p>{numbers.join(" + ")} = {sum}</p>
      <button on:click={addNumber}>Add a Number</button>
    </div>
    <div class="example2">
      <p>{numéros.join(" + ")} = {somme}</p>
      <button on:click={addNumberBetter}>Ajouter un Numéro</button>
    </div>
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
