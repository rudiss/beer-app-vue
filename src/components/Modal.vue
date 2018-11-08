<template>
  <div class="text-xs-center">
    <v-dialog v-model="dialog" width="80%">
      <v-btn slot="activator" color="blue lighten-2" dark>
        See more
      </v-btn>

      <v-card>
        <v-card-title class="headline grey lighten-2" primary-title>
          {{ name }}
        </v-card-title>
        <br>
        <v-img :src=image aspect-ratio="2" contain></v-img>
        <v-card-text>
          {{ description }}
        </v-card-text>

        <v-subheader>
          Good with:
        </v-subheader>
        <div style="display: flex">
          <v-flex v-for="(food,i) in food_pairing" :key="i">
            <div class="text-xs-center">
              <v-chip> {{ food }}</v-chip>
            </div>
          </v-flex>
        </div>
        <br>
        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" flat @click="dialog = false">
            Ok
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>
<script>
  export default {
    props: ['name', 'description', 'image', 'food_pairing'],
    data() {
      return {
        dialog: false,
      };
    },
  };
</script>