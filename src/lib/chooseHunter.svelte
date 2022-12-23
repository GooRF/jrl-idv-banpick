<script lang="ts">
    const hunters = 
["26号守卫26hsw",
"使徒st",
"博士bs",
"厂长cz",
"噩梦em",
"孽蜥nx",
"宿伞之魂sszh",
"小丑xc",
"小提琴家xtqj",
"摄影师sys",
"杰克jk",
"梦之女巫mznw",
"渔女yn",
"爱哭鬼akg",
"疯眼fy",
"破轮pl",
"红夫人hfr",
"红蝶hd",
"蜘蛛zz",
"蜡像师lxs",
"雕刻家dkj",
"鹿头lt",
"黄衣之主hyzz",] as const
    export let choice: string = ""
    export let id: string;
</script>

<select bind:value={choice} name="{id}" id={id}>
    {#each hunters as hunter}
        <option value="{hunter}">{hunter}</option>
    {/each}
</select>