<template>
  <v-item-group multiple>
    <h1 class="group-title">My Playlists</h1>
    <v-row class="cards-container">
      <v-col class="d-inline-block dimension" cols="12" mb="1">
        <v-btn
          class="create-btn"
          width="150px"
          height="150px"
          fab
          dark
          link
          to="/create"
        >
          <v-icon dark>mdi-plus</v-icon>
        </v-btn>

        <v-card-title>
          Create Playlist
        </v-card-title>
      </v-col>

      <v-col
        class="d-inline-block dimension"
        v-for="n in 4"
        :key="n"
        cols="12"
        mb="1"
      >
        <v-img
          class="round-images"
          src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
          height="150px"
          width="150px"
        ></v-img>

        <v-card-title>
          Playlist Name
        </v-card-title>
      </v-col>
    </v-row>
  </v-item-group>
</template>

<script>
export default {};
</script>

<style>
div.v-card__title {
  display: block;
  text-align: center !important;
  font-size: 0.8em;
  font-weight: normal;
  line-height: 1rem;
}
div.v-image {
  display: block;
  margin: auto;
}
.create-btn {
  display: block;
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: center;
}
.dimension {
  width: 200px !important;
  text-align: center center;
}
.round-images {
  border-radius: 1231px;
}
</style>
