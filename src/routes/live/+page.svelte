<script lang="ts">
    import Timer from "$lib/timer.svelte";
    import background from "$lib/assets/img.jpg";
    import DisplaySurvivor from "$lib/displaySurvivor.svelte";
    let timerTime = 90;
</script>

<svelte:head>
    <title>第五人格JRL赛事BP</title>
</svelte:head>

<main>
    <img src={background} alt="背景图">
    <div>
        <section class="survivors-banned-wrapper">
            {#each [1, 2, 3, 4] as n}
                <DisplaySurvivor rounded={true} survivorNum={0} />
            {/each}
        </section>
        <section class="survivor-choices-wrapper">
            {#each [1, 2, 3, 4] as n}
            <div class="survivor-profile">
                <DisplaySurvivor survivorNum={0} />
                <span id="slabel{n}">求生者{n}</span>
            </div>
            {/each}
        </section>
    </div>
</main>     

<style>
main {
    display: grid;
    overflow: hidden;
}
main > * {
    grid-row: 1;
    grid-column: 1;
}
main > div {
    position: relative;
}
img[alt="背景图"] {
    height: 100vh;
    width: 100vw;
}
.survivor-choices-wrapper {
    position: absolute;
    top: 27%;
    left: 3.5%;
    width: 50%;
    height: 58%;
    display: grid;
    grid-template-areas: 
    "1 2"
    "3 4";
    column-gap: 10%;
    row-gap: 24%;
}
.survivor-profile {
    display: flex;
    align-items: center;
}
.survivor-profile > span {
    text-align: center;
    width: 100%;
}
.survivors-banned-wrapper {
    position: absolute;
    left: 3%;
    top: 10%;
    display: flex;
    height: 11%;
    width: 27%;
    gap: 8%;
}
</style>
