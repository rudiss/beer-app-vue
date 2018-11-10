<template>
  <v-layout row>
    <v-flex xs12>
      <v-card min-height="400" max-height="500" hover style="cursor:default">
        <v-img contain :src=image height="200px">
        </v-img>
        <v-progress-circular indeterminate color="primary" 
        style=" position: absolute; left: 50%; top: 50%; transform: translate(-50%, -50%);"></v-progress-circular>
        <v-card-title primary-title>
          <div>
            <div class="headline">{{ name | truncate(15, '...')}}</div>
            <span class="grey--text">{{ tagline }}</span>
          </div>
        </v-card-title>

        <v-card-actions>
          <Modal :name=name :image=image :description=description :food_pairing=food_pairing />
          <v-spacer></v-spacer>
          <v-btn icon @click="show = !show">
            <v-icon>{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-slide-y-transition>
          <v-card-text v-show="show">
            {{ description | truncate(70, '...')}}
          </v-card-text>
        </v-slide-y-transition>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import Modal from './Modal';
  import Vue from 'vue';

  export default {
    props: ['name', 'description', 'image', 'tagline', 'food_pairing'],
    components: {
      Modal,
    },
    data: () => ({
      show: false,
    }),
  };
</script>