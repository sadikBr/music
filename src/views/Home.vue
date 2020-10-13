<template>
  <div class="home">
    <ContentGroup />
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
}
</style>
