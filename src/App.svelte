<script>
  import Info from "./Info.svelte";

  let title = "Props";
  let subtitle = "Spread Props";

  const topicPrependText = "spread-props";
  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;

  const pkg = {
    /**
     * IMPORTANTNOTE:
     * name, version, speed, website in this objects directly correspond to the props that the component takes in
     * i think i understand why the spread operator works
     * upon looking at the Svelte DevTools, Props is an object (or at least is shown as one)
     * and each prop defined is a property, with its corresponding value, that goes into that Props object
     * i am sure this is why using the spread operator works
     */
    name: "svelte",
    version: 3.0,
    speed: "blazing",
    website: "https://svelte.dev",
  };
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">If you have an object of properties, you can 'spread' them onto a component instead of specifying each one</p>
    <p class="docs__text">
      Conversely, if you need to reference all the props that were passed into a component, including ones that weren't declared with export, you can
      do so by accessing $$props directly. It's not generally recommended, as it's difficult for Svelte to optimise, but it's useful in rare cases.
    </p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink} target="_blank">Link to Docs</a>
  </div>
  <hr />
  <div class="code">
    <!-- so instead of doing this: -->
    <Info name={pkg.name} version={pkg.version} speed={pkg.speed} website={pkg.website} />
    <!-- we can do this: -->
    <Info {...pkg} />
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
</style>
