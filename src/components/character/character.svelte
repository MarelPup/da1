<script lang="ts">
    import { onMount, afterUpdate } from "svelte";
    export let char: string;
    let error = false;
    if (char === "a") {
        error = true;
    }

    afterUpdate(() => {
        if (char === " ") {
            char = "\u00A0";
        }
        if (char === "A ") {
            error = true;
        } else {
            error = false;
        }
    });
    
</script>

<span class="character" class:error>{char}</span>

<style>
    .character {
        display: inline-block;
        width: 2em;
        height: 2em;
        border: none;
        outline: 1px solid white;
        text-align: center;
        line-height: 2em ;
        font-size: 2em;
        margin: 0 6px;
    }
    .error {
        background-color: red;
    }
</style>
