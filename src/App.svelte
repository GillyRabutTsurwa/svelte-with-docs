<script>
  let title = "Introduction";
  let subtitle = "Dynamic Attributes";

  const currentTutoLink = "https://svelte.dev/tutorial/adding-data";
  const portfolioSite = "https://gilbertrabuttsurwa.tech";

  const href = "https://github.com/GillyRabutTsurwa";
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">We can use curly braces inside HTML attributes as well.</p>
    <p class="docs__text">This way, we can assign variabalise and make HTML attributes more dynamic, on top of just text</p>
    <p class="docs__text">In summary, this is pretty much the same concept as the last branch, but with attributes instead.</p>
    <p class="docs__text">
      I actually already used this in the last branch, upon defining the link for the current tutorial in the Svelte documentation. I am adding one
      more link to further clarify things.
    </p>
    <h4>One More Thing:</h4>
    <p class="docs__text">
      It's not uncommon to have an attribute where the name (HTML attribute name) and value (Javascript variable name) are the same. If this is the
      case, there is a <span class="underline">shorthand syntaxe</span> Observe the code for the third link tag:
    </p>
  </div>
  <hr />
  <div class="links">
    <a href={currentTutoLink}>Link to Docs</a>
    <a href={portfolioSite}>Gil's Portfolio Site</a>

    <!-- so, with the shorthand method, instead of doing this: -->
    <!-- <a href={href}>GitHub Settings</a> -->
    <!-- we do: -->
    <a {href}>GitHub Settings</a>
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

  .links > * {
    margin-right: 3em;
  }

  .underline {
    text-decoration: underline;
  }
</style>
