<template>
  <div class="home">
    <ContentGroup title="Trending Songs" />
    <ContentGroup title="Latest Songs" />
    <ContentGroup title="Recommended Songs" />
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

<style scoped lang="scss">
.home {
  width: 100%;
  height: 100%;
  padding: 12px;
}
</style>
