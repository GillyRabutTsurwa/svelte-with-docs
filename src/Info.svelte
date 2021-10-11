<script>
  export let name;
  export let version;
  export let speed;
  export let website;
</script>

<p>
  The <code>{name}</code> package is {speed} fast. Download version {version} from
  <a href="https://www.npmjs.com/package/{name}" class="underline">npm</a>
  and <a href={website} class="underline">learn more here</a>
</p>

<style>
  .underline {
    text-decoration: underline;
  }
</style>
