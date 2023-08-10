<script>
  import { emoji } from "./emojis";

  let state = "start";
  let size = 20;
  let grid = createGrid();
  let maxMatches = grid.length / 2;
  let selected = [];
  let matches = [];

  function createGrid() {
    let cards = new Set();
    let maxSize = size / 2;

    while (cards.size < maxSize) {
      const randomIndex = Math.floor(Math.random() * emoji.length);
      cards.add(emoji[randomIndex]);
    }
    return shuffle([...cards, ...cards]);
  }

  function shuffle(array) {
    return array.sort(() => Math.random() - 0.5);
  }
</script>

{#if state === "start"}
  <h1>Matching game</h1>
  <button on:click={() => (state = "playing")}>Play</button>
{/if}

{#if state === "playing"}
  <div class="cards">
    {#each grid as card}
      <button class="card">
        <div>{card}</div>
      </button>
    {/each}
  </div>
{/if}
