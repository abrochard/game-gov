<script>
 import Game from './Game.svelte';
</script>

<style>

 .header {
   background: #004365;
   font-size: 30px;
   padding: 5px;
   color: #fff;
 }

 .separator {
   background: #012f46;
   height: 10px;
 }

 .grid {
   display: flex;
   flex-direction: column;
   max-width: 100%;
   overflow: hidden;
 }

</style>

<div>
  <div class="header">Game Opinion Validator</div>
  <div class="separator"></div>
  <div class="grid">
    {#each Array(10) as _}
      <Game id="hyper-light-drifter"/>
      <Game id="assassins-creed-odyssey"/>
    {/each}
  </div>
</div>
