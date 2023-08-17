<script lang="ts">
  import CharaterRow from "../components/character/charater-row.svelte";
  let line1Length = 7;
  let line2Length = 7;
  let line3Length = 4;
  let ttp = "";
  let line1 = "";
  let line2 = "";
  let line3 = "";
  const handleInput = (e) => {
    ttp = e.target.value;
    //remove linebreak 
    ttp = ttp.replace(/(\r\n|\n|\r)/gm, "");
    ttp = ttp.toUpperCase();
    line1 = ttp.slice(0, line1Length);
    line2 = ttp.slice(0 + line1Length, 0 + line1Length + line2Length);
    line3 = ttp.slice(
      0 + line1Length + line2Length,
      0 + line1Length + line2Length + line3Length
    );
  };
</script>

<div class="wrapper">
  <div class="board">
    <CharaterRow lineLength={line1Length} line={line1} />
    <CharaterRow lineLength={line2Length} line={line2} />
    <CharaterRow lineLength={line3Length} line={line3} />
  </div>
  <textarea rows="3" cols="7" name="ttp" on:input={handleInput} />
</div>

<style>
  :global(body, body *) {
    background-color: #272727;
    color: white;
    outline-color: white;
  }
  .board{
    flex: 1 1 75vh;
    display: flex;
    flex-direction: column ;
    justify-content: center;
    align-items: center;
  }
  textarea{
    flex: 1 1 15vh;
    margin: 0 5vh; /* consoom 25 vh but no more*/
    padding: 0;
    border: none;
    outline:2px solid white;
  }
  .wrapper {
    display: flex;
    flex-direction: column;
    max-height: 100vh;
  }

  textarea {
    resize: none;
  }
</style>
