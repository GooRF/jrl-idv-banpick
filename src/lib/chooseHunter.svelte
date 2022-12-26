<script lang="ts">
    import { huntersList } from "./assets/huntersList";
    export let choice: string = ""
    export let id: string;
</script>

<select bind:value={choice} name="{id}" id={id}>
    {#each huntersList as hunter}
        <option value="{hunter}">{hunter}</option>
    {/each}
</select>