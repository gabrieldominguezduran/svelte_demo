<script>
  let name = "Gabo";
  let age = 48;

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
  <h1>
    Hello, my name is {name}{name.length > 3 ? "!" : ""} and I'm {age} years old!
  </h1>
  <input type="text" placeholder="Change name" on:input={handleNameChange} />
  <button on:click={incrementAge}>Increment age</button>
  <button on:click={decrementAge}>Decrement age</button>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 95dvh;
    border: 5px solid crimson;
  }
  h1 {
    color: crimson;
    margin: 0 auto;
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
