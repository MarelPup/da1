<script language="typescript">
  let line1 = "";
  
  const handleInput = (e) => {
    line1 = e.target.value;
  };


  

</script>

<h1>Hello name</h1>

<input type="text" name="line1" on:input={handleInput} />
<p>{line1}</p>


<div class=" 7-characters line line1 ">
{#each Object.entries(line1) as c}
  <span class="character" data-line1 = {c[0]} >{c[1]}</span>  
{/each}
</div>

<style>

    .character
    .line{
      display:flex;
      flex-direction: row;
    }

    :global(body) {
        background-color: #deadbeef;
    }
</style>