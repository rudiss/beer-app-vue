<template>
  <div>
    <Carousel />
    <BeerList />
  </div>
</template>

<script>
import Carousel from '../components/Carousel.vue';
import BeerList from '../components/BeerList.vue';

export default {
  components: {
    Carousel,
    BeerList,
  },
};
</script>
