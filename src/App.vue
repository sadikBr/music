<template>
  <v-app id="inspire">
    <v-navigation-drawer class="d-none d-sm-flex" v-model="drawer" app clipped>
    </v-navigation-drawer>

    <v-app-bar app clipped-left color="red" dense>
      <v-app-bar-nav-icon
        class="d-none d-sm-flex"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-icon class="mx-4 ml-0" large>
        mdi-music
      </v-icon>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">Music Player</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-row align="center" style="max-width: 650px">
        <v-text-field
          :append-icon-cb="() => {}"
          placeholder="Search..."
          single-line
          append-icon="mdi-magnify"
          color="white"
          hide-details
        ></v-text-field>
      </v-row>
    </v-app-bar>

    <v-main>
      <router-view />
      <v-bottom-navigation
        v-model="bottomNav"
        class="d-flex d-sm-none position"
        :background-color="color"
        dark
        shift
      >
        <v-btn>
          <span>Video</span>
          <v-icon>mdi-television-play</v-icon>
        </v-btn>

        <v-btn>
          <span>Music</span>
          <v-icon>mdi-music-note</v-icon>
        </v-btn>

        <v-btn>
          <span>Book</span>
          <v-icon>mdi-book</v-icon>
        </v-btn>

        <v-btn>
          <span>Image</span>
          <v-icon>mdi-image</v-icon>
        </v-btn>
      </v-bottom-navigation>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  data: () => ({
    drawer: false,
    bottomNav: 0,
  }),
  computed: {
    color() {
      let col;
      switch (this.bottomNav) {
        case 0:
          col = '#960018';
          break;
        case 1:
          col = '#B22222';
          break;
        case 2:
          col = '#7E191B';
          break;
        case 3:
          col = '#5E1914';
          break;
      }
      return col;
    },
  },
  created() {
    this.$vuetify.theme.dark = true;
  },
};
</script>

<style lang="scss">
*::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
* {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}

.position {
  position: sticky !important;
  bottom: 0 !important;
  left: 0 !important;
  right: 0 !important;
}
</style>
