<template>
  <v-app>
    <v-content>
      <v-container>
        <template>
          <v-toolbar dark>
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title>Beer App</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
              <v-btn flat>Home</v-btn>
              <v-btn flat>About</v-btn>
            </v-toolbar-items>
          </v-toolbar>
        </template>
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