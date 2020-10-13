<template>
  <v-item-group multiple>
    <v-container>
      <h1>Trending Songs</h1>
      <v-row class="cards-container">
        <v-col
          class="d-inline-block dimensions"
          v-for="n in 5"
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
                <v-col class="padding" cols="9">
                  <v-card-title>
                    Top western road trips
                  </v-card-title>

                  <v-card-subtitle>
                    1,000 miles of wonder
                  </v-card-subtitle>
                </v-col>
                <v-col class="padding" cols="3">
                  <v-icon class="pointer">mdi-play</v-icon>
                </v-col>
              </v-row>
            </v-card>
          </v-item>
        </v-col>
      </v-row>
    </v-container>
  </v-item-group>
</template>

<script>
export default {};
</script>

<style lang="scss">
.cards-container {
  display: inline-block !important;
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
.pointer {
  cursor: pointer;
}
</style>
