<template>
  <v-app>
    <v-content>
      <v-container>
        <Carousel />
        <!-- <NavigationBar /> -->

        <BeerList />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  import Carousel from './components/Carousel.vue';
  import NavigationBar from './components/NavigationBar.vue';
  import BeerList from './components/BeerList.vue';

  export default {
    name: 'App',
    components: {
      Carousel,
      NavigationBar,
      BeerList,
    },
    data() {
      return {
        //
      };
    },
  };
</script>