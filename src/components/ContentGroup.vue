<template>
  <v-item-group multiple>
    <v-container>
      <h1>Trending Songs</h1>
      <v-row>
        <v-col v-for="n in 5" :key="n" cols="12" md="4">
          <v-item>
            <v-card class="mx-auto" light>
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
                height="200px"
              ></v-img>

              <v-row align="center">
                <v-col cols="10">
                  <v-card-title>
                    Top western road trips
                  </v-card-title>

                  <v-card-subtitle>
                    1,000 miles of wonder
                  </v-card-subtitle>
                </v-col>
                <v-col cols="2">
                  <v-icon class="pointer">mdi-pause</v-icon>
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

<style>
.pointer {
  cursor: pointer;
}
</style>
