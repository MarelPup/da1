<script lang="ts">
    import Character from "./character.svelte";
    export let lineLength: number;
    export let line: string;
    // line is only space until it's char
    $: while (line.length < lineLength) {
        line += " ";
    }
</script>

<div class="line">
    {#each Object.entries(line) as c}
        <Character char={c[1]} />
    {/each}
</div>

<style>
    .line {
        z-index: 1;
        background-color: rgba(27, 27, 27, 0.75);
        display: flex;
        flex-direction: row;
        padding: 20px 0;
    }
</style>
