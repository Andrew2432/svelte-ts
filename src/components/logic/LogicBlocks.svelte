<script lang="ts">
  interface Names {
    id: number;
    name: string;
  }

  let names: Names[] = [
    { id: 1, name: 'Andrew' },
    { id: 2, name: 'Joel' },
  ];

  const removeItem = (): void => {
    names = names.slice(1);
  };
</script>

<style>
  .logic {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    justify-content: center;
  }

  table * {
    border: 1px solid #00f;
    padding: 1rem;
  }
</style>

<section class="logic">
  <h3>Names of people</h3>
  <table>
    <caption>
      <p>Table of names</p><br />
      <button on:click={removeItem}>Remove item</button>
    </caption>
    <thead>
      <th>Index</th>
      <th>ID</th>
      <th>Name</th>
    </thead>
    <tbody>
      {#each names as { id, name }, index}
        <tr>
          <td>{index}</td>
          <td>{id}</td>
          <td>{name}</td>
        </tr>
      {/each}
    </tbody>
  </table>
</section>
