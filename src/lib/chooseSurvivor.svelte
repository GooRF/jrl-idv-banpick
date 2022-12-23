<script lang="ts">
    const survivors = [
  '佣兵yb',       '先知xz',
  '入殓师rls',    '冒险家mxj',
  '击球手jqs',    '前锋qf',
  '勘探员kty',    '医生ys',
  '咒术师zss',    '哭泣小丑kqxc',
  '囚徒qt',       '园丁yd',
  '大副df',       '守墓人smr',
  '小女孩xnh',    '小说家xsj',
  '幸运儿xye',    '律师ls',
  '心理学家xlxj', '慈善家csj',
  '昆虫学者kcxz', '机械师jxs',
  '杂技演员zjyy', '牛仔nz',
  '玩具商wjs',    '画家hj',
  '病患bh',       '盲女mn',
  '祭司js',       '空军kj',
  '舞女wn',       '调酒师tjs',
  '调香师txs',    '邮差yc',
  '野人yr',       '魔术师mss'
] as const
    export let choice: string = ""
    export let id: string;
</script>

<select bind:value={choice} name="{id}" id={id}>
    {#each survivors as survivor}
        <option value="{survivor}">{survivor}</option>
    {/each}
</select>