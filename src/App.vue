<template>
  <v-app>
    <v-content>
      <NavigationBar />
      <v-container fluid>
        <router-view></router-view>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
  import NavigationBar from './components/NavigationBar.vue';

  export default {
    name: 'App',
    components: {
      NavigationBar,
    },
    data() {
      return {
        //
      };
    },
  };
</script>