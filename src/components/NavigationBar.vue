<template>
  <v-layout wrap class="black">
    <v-container>
      <v-layout justify-start align-center>

        <v-toolbar-side-icon style="color: white" @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        <h2 style="color: white">Beer App</h2>
      </v-layout>
    </v-container>

    <v-navigation-drawer v-model="drawer" :mini-variant="mini" absolute dark temporary>
      <v-list class="pa-1">
        <v-list-tile v-if="mini" @click.stop="mini = !mini">
          <v-list-tile-action>
            <v-icon>chevron_right</v-icon>
          </v-list-tile-action>
        </v-list-tile>

        <v-list-tile avatar tag="div">
          <v-list-tile-avatar>
            <img src="https://us.123rf.com/450wm/rrraven/rrraven1403/rrraven140300266/26428188-beer-icon.jpg?ver=6">
          </v-list-tile-avatar>

          <v-list-tile-content>
            <v-list-tile-title>Beer App</v-list-tile-title>
          </v-list-tile-content>

          <v-list-tile-action>
            <v-btn icon @click.stop="mini = !mini">
              <v-icon>chevron_left</v-icon>
            </v-btn>
          </v-list-tile-action>
        </v-list-tile>
      </v-list>

      <v-list class="pt-0" dense>
        <v-divider light></v-divider>

        <v-list-tile v-for="item in items" :key="item.title">
          <router-link class="v-list__tile v-list__tile--link theme--dark"
           style="padding:0; width: 100%"
           :to="item.route">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>

          <v-list-tile-content>
            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
          </v-list-tile-content>
          </router-link>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
  </v-layout>
</template>

<script>
export default {
  data() {
    return {
      drawer: null,
      items: [{
        title: 'Home',
        icon: 'dashboard',
        route: 'home',
      },
      {
        title: 'About',
        icon: 'contacts',
        route: 'about',
      },
      ],
      mini: false,
      right: null,
    };
  },
};
</script>
