<template>
  <v-list class="ma-auto" max-width="950px" subheader>
    <v-subheader>{{ groupName }}</v-subheader>

    <v-list-item v-for="n in 10" :key="n" link to="/play">
      <v-list-item-avatar>
        <v-img
          src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
        ></v-img>
      </v-list-item-avatar>
      <v-list-item-content>
        <v-list-item-content>
          <v-list-item-title v-text="songName"></v-list-item-title>
          <v-list-item-title v-text="artistName"></v-list-item-title>
        </v-list-item-content>
      </v-list-item-content>
      <v-list-item-icon>
        <v-btn class="btn-edit" x-small fab>
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
        <v-btn class="btn-edit" x-small fab>
          <v-icon>mdi-heart</v-icon>
        </v-btn>
        <v-btn class="btn-edit" fab x-small to="/play">
          <v-icon>mdi-play</v-icon>
        </v-btn>
      </v-list-item-icon>
    </v-list-item>
  </v-list>
</template>

<script>
export default {
  props: ['songName', 'artistName', 'groupName'],
};
</script>

<style scoped>
.btn-edit {
  margin: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.v-list-item__icon {
  align-self: center !important;
}
</style>
