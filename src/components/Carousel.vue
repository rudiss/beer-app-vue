<template>
  <v-container>
    <v-carousel>
      <v-progress-circular v-if="loading" indeterminate :size="70" color="primary" 
        style="position: absolute; left: 50%; margin-top: 20%; transform: translate(-50%, -20%);"
      />
      <v-carousel-item contain v-for="(item,i) in beersImg" :key="i" :src="item.image_url"></v-carousel-item>
    </v-carousel>
  </v-container>
</template>

<script>
  import axios from 'axios';

  export default {
    created() {
      const vm = this;
      vm.loading = true;
      axios
        .get('https://api.punkapi.com/v2/beers?per_page=8')
        .then((response) => {
          vm.beersImg = response.data;
          setTimeout(() => {
            vm.loading = false;
          }, 800);
        });
    },
    data() {
      return {
        beersImg: this.beersImg,
      };
    },
  };
</script>