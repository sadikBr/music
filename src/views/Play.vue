<template>
  <div class="player">
    <TopBar />
    <MainPlayer />
  </div>
</template>

<script>
import TopBar from '../components/media player/TopBar';
import MainPlayer from '../components/media player/MainPlayer';

export default {
  components: {
    TopBar,
    MainPlayer,
  },
  mounted() {
    //console.log(this.$route.params.id);
  },
};
</script>

<style scoped>
.player {
  width: 100%;
  max-height: 100%;
  overflow: hidden !important;
}
</style>
