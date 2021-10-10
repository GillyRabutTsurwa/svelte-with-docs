<script>
  let title = "Introduction";
  let subtitle = "Adding Data";

  const name = "Gilbert";
  const age = 25;
  const nationalité = "Kenyain";
  const langues = ["Anglais", "Swahili", "Francais"];
  const gagnePain = "Developpeur";
  const estBeau = true;
  const currentTutoLink = "https://svelte.dev/tutorial/adding-data";
</script>

<main>
  <div class="docs">
    <h1 class="docs__title">{title}</h1>
    <h2 class="docs__subtitle">{subtitle}</h2>
    <p class="docs__text">A component that just renders some static markup isn't very interesting. Let's add some data.</p>
    <p class="docs__text">First, add a script tag to your component and declare variable, and declare it in the markup</p>
    <p class="docs__text">Inside the curly braces, we can put any JavaScript we want.</p>
    <p>Visit the <a href="https://svelte.dev/tutorial" target="_blank">Svelte tutorial</a> to learn how to build Svelte apps.</p>
  </div>
  <hr />
  <div class="examples">
    <p>Je m'appelle {name}</p>
    <p>Vous m'entendez pas ? Je dis que je m'appelle {name.toUpperCase()}</p>
    <p>J'ai {age} ans</p>
    <p>Je suis {nationalité} et je peux parler: {langues.join(", ")}</p>
    <p>Ma profession, c'est {gagnePain}</p>
    <p>Les femmes disent que je suis {estBeau ? "beau" : "laide (quels mensonges)"}</p>
  </div>
  <div class="links">
    <a href={currentTutoLink}>Link to Docs</a>
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
</style>
