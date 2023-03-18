<script lang="ts">
  const year = new Date().getFullYear();
  const yearStart = new Date(new Date().getFullYear(), 0, 1);
  const days: Date[] = [];

  for (let i = 0; i < 365; i++) {
    const date = new Date(year, 0, i + 1);
    days.push(date);
  }

  const weeksInYear = Math.floor(days.length / 7);
  console.log(weeksInYear);
</script>

<h1>{year}</h1>
<main>
  {#each days as day}
    <div></div>
  {/each}
</main>

<style>
  main {
    width: 100%;
    display: grid;
    grid-template-columns: repeat(52, 10px);
    gap: 5px
  }
  main > div {
    border: 1px solid black;
    width: 10px;
    height: 10px;
  }
  main > div:hover {
    background: #ccc;
    cursor: pointer;
  }
</style>
