<script>
 import feather from 'feather-icons';
 import { onMount } from 'svelte';

 export let name;
 export let height = 24;

 const svg = feather.icons[name].toSvg({height: `${height}px`, width: `${height}px`});
</script>

{@html svg}
