<template>
  <div class="search">
    <SongsList groupName="Search Results" :songs="searchResults" />
  </div>
</template>

<script>
import axios from 'axios';
import SongsList from '../components/SongsList';

export default {
  components: {
    SongsList,
  },
  data() {
    return {
      searchResults: [],
    };
  },
  methods: {
    getSearchResults(term) {
      return axios.get('https://www.googleapis.com/youtube/v3/search', {
        params: {
          part: 'snippet',
          maxResults: 25,
          q: term,
          videoCategoryId: 10,
          type: 'video',
          key: 'AIzaSyB_kAo2_rPkpb90qM4p--nBdenKtG2344Y',
        },
      });
    },
  },
  watch: {
    $route(to) {
      if (to.name === 'Search') {
        this.getSearchResults(this.$route.params.q).then(
          (result) => (this.searchResults = result.data.items)
        );
      }
    },
  },
  mounted() {
    this.getSearchResults(this.$route.params.q).then(
      (result) => (this.searchResults = result.data.items)
    );
  },
};
</script>

<style>
.search {
  width: 100%;
  height: 100%;
  padding: 12px;
}
</style>
