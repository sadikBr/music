<template>
  <div class="top-bar">
    <h1>
      <v-app-bar-nav-icon
        class="nav-icon"
        @click.stop="drawer = !drawer"
      ></v-app-bar-nav-icon>
      Now Playing
    </h1>
    <v-navigation-drawer v-model="drawer" absolute bottom temporary>
      <v-list nav dense>
        <h5 class="title">Up Comming Songs</h5>
        <v-list-item-group>
          <v-list-item class="border" v-for="n in 25" :key="n" link>
            <v-list-item-avatar width="45px" height="45px">
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
              ></v-img>
            </v-list-item-avatar>
            <v-list-item-content>
              <v-list-item-content>
                <v-list-item-title v-text="songName"></v-list-item-title>
                <v-list-item-title
                  class="font"
                  v-text="artistName"
                ></v-list-item-title>
              </v-list-item-content>
            </v-list-item-content>
            <v-list-item-icon>
              <v-btn class="btn-edit" x-small fab>
                <v-icon>mdi-dots-vertical</v-icon>
              </v-btn>
              <v-btn
                class="btn-edit"
                fab
                x-small
                :to="{ name: 'Play', params: { id: n } }"
              >
                <v-icon>mdi-play</v-icon>
              </v-btn>
            </v-list-item-icon>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      volume: 0.5,
      min: 0,
      max: 1,
      songName: 'The Song Name Here',
      artistName: 'Artist Name',
    };
  },
};
</script>

<style scoped lang="scss">
.border {
  border-bottom: 1px solid rgb(122, 120, 120);
  margin-bottom: 4px;
}
.btn-edit {
  margin: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.top-bar {
  width: 100%;
  height: 10vh;
  padding: 0 10px;
  display: flex;
  align-items: center;

  h1 {
    font-size: 1.2em;
    font-weight: normal;
    display: flex;
    align-items: center;
    flex: 1;

    .nav-icon {
      margin-right: 5px;
    }
  }
}
.title {
  font-size: 0.8em !important;
  font-weight: 400;
  margin-bottom: 8px;
}
</style>
