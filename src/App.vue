<template>
<v-app>
  <v-card
    height="1020"
    dense
    app
  >
    <v-app-bar
      color="deep-purple"
      src="https://images2.alphacoders.com/774/774364.jpg"
      dark
    >
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-title>Jenkins Tutorial</v-title>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
      dark
      src="https://images2.alphacoders.com/774/774364.jpg"
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="deep-purple--text text--accent-4"
        >
          <v-list-item to="/">
            <v-list-item-title>Inicio</v-list-item-title>
          </v-list-item>

          <v-list-item to="/informacion">
            <v-list-item-title>Gráfico</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    
    <v-container class="mt-7" style="width: 2000px;">
      <router-view />
    </v-container>

    <v-footer
      :padless="true"
      dark
      fixed
      height = 110
      width = "100%"
      >
        <v-card
          flat
          tile
          width="100%"
          dark
          class="text-center"
        >
          <v-card-text>
            <v-btn to = "/home" icon>
              <v-icon>
                mdi-home
              </v-icon>
            </v-btn>
          </v-card-text>

          <v-divider></v-divider>

          <v-card-text class="white--text">
            {{ new Date().getFullYear() }} — <strong>VoluntariApp</strong>
          </v-card-text>
        </v-card>
      </v-footer>
  </v-card>
</v-app>
</template>


<script>
  export default {
    name: "app",
    data: () => ({
      drawer: false,
      group: null,
    }),
  }
</script>

<style>

  .mt-7 {
    margin-top: 80px !important;
  }

</style>