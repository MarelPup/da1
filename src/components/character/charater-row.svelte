<script lang="ts">
    import Character from "./character.svelte";
    export let lineLength: number;
    export let line: string;
    //https://stackoverflow.com/questions/62698421/svelte-adding-a-class-to-a-div-doesnt-add-the-classes-css-to-div
    
    // line is only space until it's char
    $: while (line.length < lineLength) {
      line += " ";
     
    }

</script>


<p>{lineLength}</p>

<div class="7-characters newline line">
    
    {#each Object.entries(line) as c }
        <Character char={c[1]}/>
    {/each}
</div>

<style>

    .line {
        background-color: #272727;
    }

    .newline {
        display: flex;
        flex-direction: row;
    }
</style>
