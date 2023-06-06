<script lang="ts">
  import CharaterRow from "../components/character/charater-row.svelte";
</script>

<h1>Hello name</h1>
  <CharaterRow />

<style>


  :global(body, body *) {
    background-color: #272727;
    color: white;
    outline-color: white;
  }
  :global(.error){
    background-color: red;
  }
</style>
