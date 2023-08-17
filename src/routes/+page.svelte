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
    line1 = ttp.slice(0, line1Length);
    line2 = ttp.slice(0 + line1Length, 0 + line1Length + line2Length);
    line3 = ttp.slice(
      0 + line1Length + line2Length,
      0 + line1Length + line2Length + line3Length
    );
  };
</script>

<div class="wrapper">
  <textarea rows="3" cols="7" name="ttp" on:input={handleInput} />
  <CharaterRow lineLength={line1Length} line={line1} />
  <CharaterRow lineLength={line2Length} line={line2} />
  <CharaterRow lineLength={line3Length} line={line3} />
</div>

<style>
  :global(body, body *) {
    background-color: #272727;
    color: white;
    outline-color: white;
  }

  .wrapper {
    display: flex;
    flex-direction: row;
  }
  .wrapper {
    flex: 1;
  }
  textarea {
    position: absolute;
    bottom: 0;
    resize: none;
  }
</style>
