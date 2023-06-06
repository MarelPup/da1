
<script lang="ts">
      //https://stackoverflow.com/questions/62698421/svelte-adding-a-class-to-a-div-doesnt-add-the-classes-css-to-div
  let line1 = "       ";

const handleInput = (e) => {
  line1 = e.target.value;

  if (line1.length > 7) {
    line1 = line1.substring(0, 7);
  }
  while (line1.length < 7) {
    line1 += " ";
  }

  for (let i = 0; i < line1.length; i++) {
    const char = line1[i];
    const el = document.querySelector(`[data-line1="${i}"]`);
    if (el) {
      if (line1[i] === "a") {
        el.classList.add("error");
      } else {
        if (el.classList.contains("error")) {
          el.classList.remove("error");
        }
      }
    }
  }
};
</script>

<input type="text" name="line1" on:input={handleInput} />
<p>{line1}</p>

<div class=" 7-characters line line1">
  {#each Object.entries(line1) as c}
    <span class="character" data-line1={c[0]}>{c[1]}</span>
  {/each}
</div>

<style>
    .character {
        display: inline-block;
        width: 1em;
        height: 1em;
        border: 1px solid white;
        margin: 0.1em;
        text-align: center;
        line-height: 1em;
        font-size: 1em;
    }
    .line1 {
        background-color: #272727;
    }

    .line {
        display: flex;
        flex-direction: row;
    }
</style>
 