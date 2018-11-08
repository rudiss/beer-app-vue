<template>
<v-container>
  <v-carousel>
    <v-carousel-item contain v-for="(item,i) in beersImg" :key="i" :src="item.image_url"></v-carousel-item>
  </v-carousel>
</v-container>
</template>

<script>
import axios from 'axios';

export default {
    created() {
    const vm = this;
    axios
      .get('https://api.punkapi.com/v2/beers?per_page=8')
      .then((response) => {
        vm.beersImg = response.data;
      });
  },
  data() {
    return {
      beersImg: this.beersImg,
    };
  },
};
</script>
