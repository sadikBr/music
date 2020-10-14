<template>
  <v-app id="inspire">
    <v-navigation-drawer class="d-none d-sm-flex" v-model="drawer" app clipped>
      <v-list dense>
        <v-list-item link to="/">
          <v-list-item-action>
            <v-icon>mdi-home</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              Home
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link to="/mymusic">
          <v-list-item-action>
            <v-icon>mdi-music</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              My Music
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link to="/favorites">
          <v-list-item-action>
            <v-icon>mdi-heart</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              Favorites
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link to="/history">
          <v-list-item-action>
            <v-icon>mdi-history</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              History
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link to="/downloads">
          <v-list-item-action>
            <v-icon>mdi-download</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>
              Downloads
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app clipped-left :color="color">
      <v-app-bar-nav-icon
        class="d-none d-sm-flex mr-3"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      <v-icon class="d-flex d-sm-none mx-4 ml-0" large>
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
        <v-btn to="/">
          <span>Home</span>
          <v-icon>mdi-home</v-icon>
        </v-btn>

        <v-btn to="/mymusic">
          <span>My Music</span>
          <v-icon>mdi-music</v-icon>
        </v-btn>

        <v-btn to="/favorites">
          <span>Favorites</span>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn to="/downloads">
          <span>Downloads</span>
          <v-icon>mdi-download</v-icon>
        </v-btn>

        <v-btn to="/history">
          <span>History</span>
          <v-icon>mdi-history</v-icon>
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

body {
  overflow: auto;
  height: 100vh;
}

.position {
  position: sticky !important;
  bottom: 0 !important;
  left: 0 !important;
  right: 0 !important;
}
</style>
