<script lang="ts">
    import Timer from "$lib/timer.svelte";
    let timerTime = 90;
</script>

<svelte:head>
    <title>第五人格JRL赛事BP</title>
</svelte:head>

<main>
    <Timer bind:time={timerTime} />
</main>     