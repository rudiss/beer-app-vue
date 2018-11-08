<template>
  <v-layout row>
    <v-flex xs12>
      <v-card min-height="400" max-height="500" hover style="cursor:default">
        <v-img contain :src=image height="200px">
        </v-img>

        <v-card-title primary-title>
          <div>
            <div class="headline">{{ name | truncate(15, '...')}}</div>
            <span class="grey--text">{{ tagline }}</span>
          </div>
        </v-card-title>

        <v-card-actions>
          <Modal :name=name :image=image :description=description />
          <v-spacer></v-spacer>
          <v-btn icon @click="show = !show">
            <v-icon>{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
          </v-btn>
        </v-card-actions>

        <v-slide-y-transition>
          <v-card-text  v-show="show">
            {{ description | truncate(70, '...')}}
          </v-card-text>
        </v-slide-y-transition>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
  import Modal from './Modal';
  export default {
    props: ['name', 'description', 'image', 'tagline'],
    components: {
      Modal
    },
    data: () => ({
      show: false
    })
  };
</script>