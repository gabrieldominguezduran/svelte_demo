<script>
  let name = "Gabo";
  let age = 48;

  function incrementAge() {
    age++;
  }

  function decrementAge() {
    age--;
  }

  function handleNameChange(event) {
    name = event.target.value;
  }
</script>

<h1>Hello, my name is {name} and I'm {age} years old!</h1>
<button on:click={incrementAge}>Increment age</button>
<button on:click={decrementAge}>Decrement age</button>
<input type="text" placeholder="Change name" on:input={handleNameChange} />

<style>
  h1 {
    color: purple;
    margin: 1rem 0.7rem;
  }

  button {
    background-color: purple;
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
    border: 1px solid purple;
    margin: 10px;
  }
</style>
