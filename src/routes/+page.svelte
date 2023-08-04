<script>
  import ContactCard from "../components/ContactCard.svelte";
  let name = "Gabo";
  let age = 48;
  let title = "";
  let description = "";

  const capitalizeName = (string) => {
    return string.charAt(0).toUpperCase() + string.slice(1);
  };

  function incrementAge() {
    age++;
  }

  function decrementAge() {
    age--;
  }

  function handleNameChange(event) {
    name = capitalizeName(event.target.value);
  }
</script>

<main>
  <section class="buttons">
    <h1>
      Hello, my name is {name}{name.length > 3 ? "!" : ""} and I'm {age} years old!
    </h1>
    <input type="text" placeholder="Change name" on:input={handleNameChange} />
    <input type="text" placeholder="Add Job title" bind:value={title} />
    <input type="text" placeholder="Add description" bind:value={description} />
    <button type="button" on:click={incrementAge}>Increment age</button>
    <button type="button" on:click={decrementAge}>Decrement age</button>
  </section>
  <section class="contact-card">
    <ContactCard userName={name} jobTitle={title} {description} />
  </section>
</main>

<style>
  main {
    height: 95dvh;
    border: 5px solid crimson;
  }

  .buttons {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: start;
  }
  h1 {
    color: crimson;
    text-align: center;
  }

  button {
    background-color: crimson;
    color: white;
    border: none;
    padding: 10px 20px;
    border-radius: 5px;
    margin: 10px;
    cursor: pointer;
  }

  input {
    padding: 10px;
    border-radius: 5px;
    border: 1px solid crimson;
    margin: 10px;
  }
</style>
