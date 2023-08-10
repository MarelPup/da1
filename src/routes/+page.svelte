<script lang="ts">
  import CharaterRow from "../components/character/charater-row.svelte";
  let prop = 25;
  let value1 = "";

  const handleInput = (e) => {
    let ttp = e.target.value;
    value1 = "zsfv"; 
  };


</script>



<div class="wrapper">
  <textarea rows=3 cols=7 name="ttp" on:input={handleInput} />
  <CharaterRow length={prop} value={value1} />
</div>

<style>
  :global(body, body *) {
    background-color: #272727;
    color: white;
    outline-color: white;
  }

  .wrapper{
    display: flex;
    flex-direction: row;
    
  }
  .wrapper{
    flex: 1;
  }
  textarea {
		position: absolute;
		top: 0;
		resize: none;
	}

</style>
