<script>
  import Nested from "./Nested.svelte";

  let title = "Props";
  let subtitle = "Declaring Props";

  const topicPrependText = "declaring-props";
  const currentTutoLink = `https://svelte.dev/tutorial/${topicPrependText}`;
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">
      So far, we've dealt exclusively with internal state — that is to say, the values are only accessible within a given component.
    </p>
    <p class="docs__text">
      In any real application, you'll need to pass data from one component down to its children. To do that, we need to declare properties, generally
      shortened to 'props'. In Svelte, we do that with the export keyword (in the child component)
    </p>
    <p class="docs__text">
      Just like <code>$:</code>, this may feel a little weird at first. That's not how export normally works in JavaScript modules! Just roll with it
      for now — it'll soon become second nature.
    </p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink} target="_blank">Link to Docs</a>
  </div>
  <hr />
  <div class="code">
    <Nested answer={27} />
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
