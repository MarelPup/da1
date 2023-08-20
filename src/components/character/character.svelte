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
        if (char === "A") {
            error = true;
        } else {
            error = false;
        }
    });
    
</script>

<span class="character graf-font" class:error>{char}</span>

<style>
    @font-face {
    font-family: "nas";
    src: url("../../fonts/no-added-sugar-font/NoAddedSugar-2REW.ttf");
}

    .character {
        display: inline-block;
        width: 1em;
        border: 3px solid white;
        padding-top: 4px;
        text-align: center;
        font-weight: bold;
        font-size: 2em;
        margin: 0 6px;
        z-index:1;
    }
    .graf-font{
        font-family: "nas";
    }
    .error {
        background-color: rgb(255,0,0);
    }
</style>
