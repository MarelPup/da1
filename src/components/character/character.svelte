<script lang="ts">
    import { onMount, afterUpdate } from "svelte";
    export let char: string;
    let error = false;
    if (char === "a") {
        error = true;
    }

    afterUpdate(() => {
        if (char === "a") {
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
        width: 1em;
        height: 1em;
        border: 1px solid white;
        margin: 0.1em;
        text-align: center;
        line-height: 1em;
        font-size: 1em;
    }
    .error {
        background-color: red;
    }
</style>
