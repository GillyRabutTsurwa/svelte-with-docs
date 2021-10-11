<script>
  import Nested from "./Nested.svelte";

  let title = "Props";
  let subtitle = "Default Values";

  const topicPrependText = "default-values";
  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">We can easily specify default values for props in Nested.svelte:</p>
    <p class="docs__text">If we now add a second component without an answer prop, it will fall back to the default</p>
    <p>I like this a lot</p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink} target="_blank">Link to Docs</a>
  </div>
  <hr />
  <div class="code">
    <Nested answer={27} />
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
