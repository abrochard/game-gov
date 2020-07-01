<script>
 export let id;

 export let content = [
   'Nullam rutrum',
   'Nam a sapien',
   'Vestibulum convallis, lorem a tempus semper, dui dui euismod elit, vitae placerat urna tortor vitae lacus',
   'Vivamus id enim',
   'Donec at pede',
   'Vestibulum convallis, lorem a tempus semper, dui dui euismod elit, vitae placerat urna tortor vitae lacus',
   'Phasellus purus',
   'Nam euismod tellus id erat',
   'Donec posuere augue in quam',
 ];


 import { slide } from 'svelte/transition';
 import Icon from './Icon.svelte';

 let up = false;
 let down = false;

 function like() {
   down = false;
   up = !up;
 }

 function dislike() {
   up = false;
   down = !down;
 }

</script>

<style>

 .card {
   display: flex;
   width: 100%;
   padding: 5px;
   background: #f2f2f2;
   margin-top: 10px;
   margin-left: 5px;
   margin-right: 5px;
 }

 .img {
   max-width: 25%;
 }

 img {
   width: 100%;
 }

 .panel {
   margin-left: 5px;
   display: flex;
   flex-direction: column;
 }

 .vote {
   display: flex;
   margin-left: auto;
   margin-right: auto;
   margin-top: 15px;
   /* margin: 15px; */
   width: 100%;
 }

 .title {
   font-size: 25px;
 }

 .content {
   word-wrap: break-word;
   max-width: 100%;
   padding-top: 20px;
 }


</style>

<div class="card">
  <div class="img">
    <img alt="{id}" src="/img/{id}.jpg"/>
  </div>
  <div class="panel">
    <div class="title">{id}</div>
    <div class="vote">
      <div on:click="{like}" style="margin-right: 20px"><Icon name="thumbs-up" /></div>
      <div on:click="{dislike}"><Icon name="thumbs-down" /></div>
    </div>

    {#if up}
      <div transition:slide class="content">
        Positive
        {#each content as line}
          <li>{line}</li>
        {/each}
      </div>
    {/if}
    {#if down}
      <div transition:slide class="content">
        Negative
        {#each content as line}
          <li>{line}</li>
        {/each}
      </div>
    {/if}
  </div>
</div>
