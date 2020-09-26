<script lang="ts">
  import LogicBlocks from './components/logic/LogicBlocks.svelte';
  import SimpleEvent from './components/reactivity/SimpleEvent.svelte';
  import Hello from './Hello.svelte';

  export let name: string;
</script>

<style>
  *,
  *::before,
  *::after {
    box-sizing: border-box;
  }

  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name}!</h1>
  <p>
    Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn
    how to build Svelte apps.
  </p>
  <Hello />
  <h2>Let's implement a counter</h2>
  <SimpleEvent count={1} />
  <hr />
  <h2>Let's use some logic statements</h2>
  <LogicBlocks />
</main>
