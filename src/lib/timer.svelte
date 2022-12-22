<script lang="ts">
    export let time: number;
    setInterval(()=>{
        time--;
    }, 1000)
</script>

<div>
    { time < 0 ? 0 : time }
</div>