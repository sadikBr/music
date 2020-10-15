<template>
  <v-item-group multiple>
    <h1 class="group-title">{{ title }}</h1>
    <v-row class="cards-container">
      <v-col
        class="d-inline-block dimensions"
        v-for="n in 15"
        :key="n"
        cols="12"
        mb="2"
      >
        <v-item>
          <v-card class="mx-auto" light>
            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
              height="150px"
            ></v-img>

            <v-row align="center">
              <v-col class="padding" cols="10">
                <v-card-title>
                  Top western road trips
                </v-card-title>

                <v-card-subtitle>
                  1,000 miles of wonder
                </v-card-subtitle>
              </v-col>
              <v-btn dark fab x-small flat to="/play">
                <v-icon>mdi-play</v-icon>
              </v-btn>
            </v-row>
          </v-card>
        </v-item>
      </v-col>
    </v-row>
  </v-item-group>
</template>

<script>
export default {
  props: ['title'],
};
</script>

<style scoped lang="scss">
.group-title {
  font-size: 1.5rem;
  font-weight: normal;
}
.cards-container {
  display: block !important;
  white-space: nowrap !important;
  overflow: auto hidden !important;
}
.dimensions {
  width: 300px !important;
}
.padding {
  padding: 0 12px !important;

  div {
    font-size: 1em !important;

    &:last-child {
      font-size: 0.8em !important;
    }
  }
}
</style>
