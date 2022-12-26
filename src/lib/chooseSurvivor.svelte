<script lang="ts">
    import { survivorsList } from "./assets/survivorsList";
    export let choice: string = ""
    export let id: string;
</script>

<select bind:value={choice} name="{id}" id={id}>
    {#each survivorsList as survivor}
        <option value="{survivor}">{survivor}</option>
    {/each}
</select>