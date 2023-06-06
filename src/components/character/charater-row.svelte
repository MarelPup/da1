<script lang="ts">
    import Character from "./character.svelte";
    export let length: number;
    //https://stackoverflow.com/questions/62698421/svelte-adding-a-class-to-a-div-doesnt-add-the-classes-css-to-div
    let line = "";
    for (let i = 0; i < length; i++) {
        line += " ";
    }

    const handleInput = (e) => {
        line = e.target.value;

        if (line.length > length) {
            line = line.substring(0, length);
        }
        while (line.length < length) {
            line += " ";
        }

    };

</script>

<input type="text" name="line" on:input={handleInput} />
<p>{line}</p>

<div class=" 7-characters newline line">
    {#each Object.entries(line) as c}
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
