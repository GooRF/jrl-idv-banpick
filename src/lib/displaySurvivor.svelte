<script lang="ts">
    import { survivorsImagesList } from "./assets/survivorsList";
    export let survivorNum: number;
    export let dimensions = [100, 100]
    export let rounded = false
</script>

<img style=
"width: {dimensions[0].toString()+'%'};
height: {dimensions[1].toString()+'%'};
{rounded ? 'border-radius: 50%': ''}"
src={survivorsImagesList[survivorNum]} alt="oh noes">