<script lang="ts">
  import CharaterRow from "../components/character/charater-row.svelte";
  import DizzyBg from "./dizzyBg.svelte";
  //disgusting conf
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
    <DizzyBg />
    <CharaterRow lineLength={line1Length} line={line1} />
    <CharaterRow lineLength={line2Length} line={line2} />
    <CharaterRow lineLength={line3Length} line={line3} />
  </div>
  <textarea name="ttp" on:input={handleInput} />
</div>

<style lang="scss">
  :global(body) {
    margin: 0;
    padding: 0;
  }
  :global(body, body *) {
    color: white;
    outline-color: white;
    background-color: #272727;
    //A80024
  }
  :global(.dizzy) {
    position: absolute;
    z-index: 0;
  }

  .board {
    flex: 1 1 75vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background: none;
  }
  textarea {
    flex: 1 1 15vh;
    margin: 5vh 5vh; /* consoom 25 vh but no more*/

    border: none;
    //outline: 2px solid white;
    z-index: 1;
    border: 2px white solid;
    font-size: 2em;
    resize: none;
    
  }
  .wrapper {
    display: flex;
    flex-direction: column;
    max-height: 100vh;
    
  }

</style>
