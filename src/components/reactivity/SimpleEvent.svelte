<script lang="ts">
  export let count = 0;
  $: doubled = count * 2;

  $: {
    console.warn('Value of count changed. I had to react to it');
    if (count > 20) {
      alert('Maximum value reached. Resetting to 0');
      count = 0;
    }
  }

  const add = (): void => {
    ++count;
  };

  const sub = (): void => {
    --count;
  };
</script>

<style>
  .counter {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    justify-content: center;
  }

  .buttons {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .buttons button {
    padding: 1rem;
    background-color: #ff00ea;
    color: #fff;
    font-size: 1.2rem;
  }
</style>

<section class="counter">
  <h2>Current value: {count}</h2>
  {#if count % 3 === 0 && count % 5 === 0}
    <p>FizzBuzz</p>
  {:else if count % 3 === 0}
    <p>Fizz</p>
  {:else if count % 5 === 0}
    <p>Buzz</p>
  {:else}
    <p>{count}</p>
  {/if}
  <h2>Reactive value: {doubled}</h2>
  <div class="buttons">
    <button on:click={add}>+</button>
    <button on:click={sub}>-</button>
  </div>
</section>
