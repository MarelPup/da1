<script lang="ts">
  import CharaterRow from "../components/character/charater-row.svelte";
  let prop = 25;
</script>

<h1>Hello name</h1>
  <CharaterRow length={prop}/>
<style>

  :global(body, body *) {
    background-color: #272727;
    color: white;
    outline-color: white;
  }

</style>
