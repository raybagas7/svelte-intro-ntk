<script>
  let name;
  let beltColor;
  let age;
  let skills = [];
  //   let fighthing = false,
  //     running = false,
  //     sneaking = false;

  const handleSubmit = () => {
    console.log(name, beltColor, age, skills);
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <input type="type" placeholder="name" bind:value={name} />
  <input type="number" placeholder="age" bind:value={age} />
  <label for="">Skills:</label>
  <!-- <input type="checkbox" bind:checked={fighthing} />fighthing<br />
  <input type="checkbox" bind:checked={sneaking} />sneaking<br />
  <input type="checkbox" bind:checked={running} />running<br /> -->
  <input type="checkbox" bind:group={skills} value="fighthing" />fighthing<br />
  <input type="checkbox" bind:group={skills} value="sneaking" />sneaking<br />
  <input type="checkbox" bind:group={skills} value="running" />running<br />
  <label for="belt">Belt Color</label>
  <select name="belt" bind:value={beltColor}>
    <option value="black">Black</option>
    <option value="orange">Orange</option>
    <option value="brown">Brown</option>
    <option value="white">White</option>
  </select>
  <button type="submit">Add Person</button>
</form>

<style></style>
