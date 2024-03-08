<script>
  let name;
  let beltColor;
  let age;

  const handleSubmit = () => {
    console.log(name, beltColor, age);
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="type" placeholder="name" bind:value={name} />
  <input type="type" placeholder="belt color" bind:value={beltColor} />
  <input type="number" placeholder="age" bind:value={age} />
  <button type="submit">Add Person</button>
</form>

<style></style>
