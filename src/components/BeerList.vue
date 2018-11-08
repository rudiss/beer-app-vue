<template>
  <div>
    <v-container grid-list-md>
      <v-layout row wrap>
        <v-flex v-for="beer in beers" :key="`${beer.id}`" xs4>
          <BeerCard
          :name=beer.name
          :description=beer.description
          :image=beer.image_url
          :tagline=beer.tagline
          :food_pairing=beer.food_pairing
           />
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
import axios from 'axios';
import BeerCard from './BeerCard.vue';
import Modal from './Modal.vue';

export default {
  created() {
    const vm = this;
    axios
      .get('https://api.punkapi.com/v2/beers')
      .then((response) => {
        vm.beers = response.data;
        let malt;
        for (const beer of response.data) {
          malt = beer.ingredients.malt
          for (const name of malt) {
            console.log(name.name);
          }
        }
         console.log(malt);
        
      });
  },
  components: {
    BeerCard,
    Modal
  },
  data() {
    return {
      beers: this.beers,
    };
  },
};
</script>
