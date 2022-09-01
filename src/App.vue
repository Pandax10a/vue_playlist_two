<template>
  <div id="app">
    <song-list></song-list>
    <play-list></play-list>
    <now-playing></now-playing>
    
  </div>
</template>

<script>
import SongList from '@/components/SongList.vue';
import PlayList from '@/components/PlayList.vue';
import NowPlaying from '@/components/NowPlaying.vue';

export default {
  components: {
    SongList,
    PlayList,
    NowPlaying
  
  },
};

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
