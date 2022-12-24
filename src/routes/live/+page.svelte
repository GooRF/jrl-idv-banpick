<script lang="ts">
    import Timer from "$lib/timer.svelte";
    import background from "$lib/assets/img.jpg";
    let timerTime = 90;
</script>

<svelte:head>
    <title>第五人格JRL赛事BP</title>
</svelte:head>

<main>
    <img src={background} alt="背景图">
    <div>
        <Timer bind:time={timerTime} />
        {#each [1, 2, 3, 4] as n}
        <div>
            <img id="simg{n}" alt="bg">
            <span id="slabel{n}">求生者{n}</span>
        </div>
        {/each}
    </div>
</main>     

<style>
main {
    display: grid;
}
main > * {
    grid-row: 1;
    grid-column: 1;
}
img[alt="背景图"] {
    height: 100vh;
    width: 100vw;
}
</style>
