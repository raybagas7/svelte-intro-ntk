<script>
  let people = [
    { name: 'Ray', beltColor: 'Black', age: 25, id: 1 },
    { name: 'Samudra', beltColor: 'Red', age: 16, id: 2 },
    { name: 'Bagas', beltColor: 'Purple', age: 18, id: 3 },
  ];

  const handleDelete = (id) => {
    // delete person from people
    people = people.filter((person) => person.id !== id);
  };

  let num = 3;
</script>

<!--- Conditional logic -->
{#if num > 20}
  <p>Greater than 20</p>
{:else if num > 5}
  <p>Greater than 5</p>
{:else}
  <p>Less than 5</p>
{/if}

<main>
  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      {#if person.beltColor === 'Black'}
        <p><strong>Master ninja</strong></p>
      {/if}
      <p>{person.age} years old, {person.beltColor} belt.</p>
      <button on:click={() => handleDelete(person.id)}>Delete</button>
    </div>
  {:else}
    <p>There are no people to show...</p>
  {/each}
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
