<script>
  import Modal from './Modal.svelte';
  import AddPersonFrom from './AddPersonFrom.svelte';
  let showModal = false;

  const toggleModal = () => {
    showModal = !showModal;
  };

  let people = [
    { name: 'Ray', beltColor: 'Black', age: 25, id: 1 },
    { name: 'Samudra', beltColor: 'Red', age: 16, id: 2 },
    { name: 'Bagas', beltColor: 'Purple', age: 18, id: 3 },
  ];

  const handleDelete = (id) => {
    // delete person from people
    people = people.filter((person) => person.id !== id);
  };

  const addPerson = (e) => {
    // you can't change the variable directly / push so you need to re asign with something new
    const person = e.detail;
    // instead you can re asign it like this with spread operator
    people = [person, ...people];
    showModal = false;
  };
</script>

<Modal isPromo={false} {showModal} on:click={toggleModal}>
  <AddPersonFrom on:addPerson={addPerson} />
</Modal>
<main>
  <button on:click={toggleModal}>Open Modal</button>
  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      {#if person.beltColor === 'Black'}
        <p><strong>Master ninja</strong></p>
      {/if}
      <p>{person.age} years old, {person.beltColor} belt.</p>
      {#if person.skills}
        {#each person.skills as skill (skill)}
          <p>{skill}</p>
        {/each}
      {/if}
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
