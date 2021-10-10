<script>
  import Nested from "./Nested.svelte";
  let title = "Introduction";
  let subtitle = "Nested Components";

  const topicPrependText = "nested-components";

  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">
      It would be impractical to put your entire app in a single component. Instead, we can import components from other files and include them as
      though we were including elements.
    </p>
    <p class="docs__text">Add a script tag that imports Nested.svelte...</p>
    <p class="docs__text">Then add it to the markup</p>
    <p class="docs__text">Notice that even though Nested.svelte has a</p>
    <p>element, the styles from App.svelte don't leak in.</p>
    <p class="docs__text">
      Also notice that the component name Nested is capitalised. This convention has been adopted to allow us to differentiate between user-defined
      components and regular HTML tags
    </p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink}>Link to Docs</a>
  </div>
  <hr />
  <div class="code">
    <Nested />
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
