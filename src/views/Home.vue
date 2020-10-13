<template>
  <div class="home">
    <ContentGroup title="Trending Songs" />
    <ContentGroup title="Popular Songs" />
    <ContentGroup title="Favorite Songs" />
    <ContentGroup title="Last Listened Songs" />
  </div>
</template>

<script>
import ContentGroup from '../components/ContentGroup';

export default {
  name: 'Home',
  components: {
    ContentGroup,
  },
};
</script>

<style lang="scss">
.home {
  width: 100%;
  height: 100%;
  padding: 12px;
  overflow: hidden auto;
}
</style>
