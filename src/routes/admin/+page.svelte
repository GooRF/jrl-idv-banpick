<script lang="ts">
    import ChooseHunter from "$lib/chooseHunter.svelte";
import ChooseSurvivor from "$lib/chooseSurvivor.svelte";

    let team1name: string
    let team2name: string

    function swap() { [ team1name, team2name ] = [ team2name, team1name ] }

    let survivorsChoices: string[] = []
    let survivorsBanned: string[] = []

    let hunterChoice: string = ""
    let huntersBanned: string[] = []

    let survivorNames: string[] = []
    let hunterName: string
</script>

<form class="flex-col" action="none" on:submit|preventDefault>    
    <fieldset>
        <legend>队伍</legend>
        <label for="team1">队伍1:</label>
        <input type="text" name="team1" id="team1" bind:value={team1name}>
        
        <label for="team2">队伍2:</label>
        <input type="text" name="team2" id="team2" bind:value={team2name}>
        
        <button on:click={swap} type="button">Swap Sides</button>
    </fieldset>
    <div class="flex-row">
        <fieldset class="flex-col">
            <legend>求生者方</legend>
            <div class="flex-col">
                {#each [1, 2, 3, 4] as n}
                <label for="s{n}">求生{n}:</label>
                <ChooseSurvivor id="s{n}" bind:choice={survivorsChoices[n-1]} />
                {/each}
            </div>
            <div class="flex-col">
                {#each [1, 2, 3, 4] as n}
                <label for="bh{n}">监管ban位{n}:</label>
                <ChooseHunter id="bh{n}" bind:choice={huntersBanned[n-1]} />
                {/each}
            </div>
        </fieldset>
        <fieldset class="flex-col">
        <legend>监管者方</legend>
        <div>
            <label for="hunter">监管者:</label>
            <ChooseHunter id="hunter" bind:choice={hunterChoice} />
        </div>
        <div class="flex-col">
            {#each [1, 2, 3, 4, 5, 6] as n}
            <label for="bs{n}">求生ban位{n}</label>
            <ChooseSurvivor id="bs{n}" bind:choice={survivorsBanned[n-1]}  />
            {/each}
        </div>
    </fieldset>
    <fieldset class="flex-col">
        <legend>选手信息</legend>
        {#each [1, 2, 3, 4] as n}
        <label for="sn{n}">求生者选手{n}名字</label>
        <input type="text" name="sn{n}" id="sn{n}">
        {/each}
        <label for="hn">监管者选手名字</label>
        <input type="text" name="hn" id="hn">
    </fieldset>
    </div>
</form>

<style>
.flex-col {
    display: flex;
    flex-direction: column;
    width: min-content;
}
.flex-row {
    display: flex;
    flex-direction: row;
}
</style>