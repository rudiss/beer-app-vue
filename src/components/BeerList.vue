<template>
  <div>
    <v-container grid-list-md>
      <BeerFilter />
      <v-layout row wrap>
        <v-flex v-for="beer in beers" :key="`${beer.id}`" xs4>
        <v-progress-circular v-if="loading" indeterminate color="primary"></v-progress-circular>

          <BeerCard :name=beer.name :description=beer.description :image=beer.image_url :tagline=beer.tagline
            :food_pairing=beer.food_pairing />
        </v-flex>
      </v-layout>
      <a href=""></a>
    </v-container>
  </div>
</template>

<script>
  import axios from 'axios';
  import BeerCard from './BeerCard.vue';
  import BeerFilter from './BeerFilter.vue';
  import Modal from './Modal.vue';
  import _ from 'lodash';

  export default {
    created() {
      const vm = this;
      vm.gtAlcohol = 0;
      vm.ltAlcohol = 100;
      vm.loading = true;
      axios
        .get(`https://api.punkapi.com/v2/beers?abv_gt=${vm.gtAlcohol}&abv_lt=${vm.ltAlcohol}`)
        .then((response) => {
          vm.beers = response.data;
          for (const beer of response.data) {
            const acNivel = beer.abv;
            console.log(acNivel);
          }
          vm.loading = false;
        });
    },
    components: {
      BeerCard,
      Modal,
      BeerFilter
    },
    data() {
      return {
        beers: this.beers,
        loading: this.loading,
      };
    },
  };
</script>