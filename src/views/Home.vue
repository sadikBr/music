<template>
  <div class="home">
    <v-progress-circular
      class="d-block mt-12 mx-auto"
      v-if="loading"
      :size="70"
      :width="7"
      color="red"
      indeterminate
    ></v-progress-circular>
    <ContentGroup
      v-if="!loading"
      title="Trending Songs"
      :data="moroccoMostPopularVideos"
    />
    <ContentGroup
      v-if="!loading"
      title="You Could Also Like"
      :data="bollywoodMostPopularVideos"
    />
    <ContentGroup v-if="!loading" title="Top Songs" :data="topSongs" />
  </div>
</template>

<script>
import axios from 'axios';
import ContentGroup from '../components/ContentGroup';

export default {
  name: 'Home',
  components: {
    ContentGroup,
  },
  data() {
    return {
      loading: true,
      moroccoMostPopularVideos: [],
      bollywoodMostPopularVideos: [],
      topSongs: [],
    };
  },
  methods: {
    getMoroccoMostPopular() {
      return axios.get('https://www.googleapis.com/youtube/v3/videos', {
        params: {
          part: 'snippet',
          chart: 'mostPopular',
          maxResults: 20,
          regionCode: 'ma',
          videoCategoryId: '10',
          key: 'AIzaSyB_kAo2_rPkpb90qM4p--nBdenKtG2344Y',
        },
      });
    },
    getBollywoodMostPopular() {
      return axios.get('https://www.googleapis.com/youtube/v3/videos', {
        params: {
          part: 'snippet',
          chart: 'mostPopular',
          maxResults: 20,
          regionCode: 'in',
          videoCategoryId: '10',
          key: 'AIzaSyB_kAo2_rPkpb90qM4p--nBdenKtG2344Y',
        },
      });
    },
    getTopSongs() {
      return axios.get('https://www.googleapis.com/youtube/v3/playlistItems', {
        params: {
          part: 'snippet',
          maxResults: 20,
          playlistId: 'PL64E6BD94546734D8',
          key: 'AIzaSyB_kAo2_rPkpb90qM4p--nBdenKtG2344Y',
        },
      });
    },
  },
  mounted() {
    console.log(process.env.VUE_APP_API_KEY);
    Promise.all([
      this.getMoroccoMostPopular(),
      this.getBollywoodMostPopular(),
      this.getTopSongs(),
    ]).then((results) => {
      this.loading = false;
      this.moroccoMostPopularVideos = results[0].data.items;
      this.bollywoodMostPopularVideos = results[1].data.items;
      this.topSongs = results[2].data.items;
    });
  },
};
</script>

<style scoped lang="scss">
.home {
  width: 100%;
  height: 100%;
  padding: 12px;
}
</style>
