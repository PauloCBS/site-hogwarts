<template>
  <div class="App-top-bar">
      <v-app-bar
      color="blue-grey lighten-1"
      dark
      app
    >
      <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>

      <v-toolbar-title class="font-weight-black">
          <div>Hogwarts</div>
          </v-toolbar-title>

    <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-lightning-bolt-outline</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-auto-fix</v-icon>
      </v-btn>

      <v-menu
        left
        bottom
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            icon
            v-bind="attrs"
            v-on="on"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="n in 5"
            :key="n"
            @click="() => {}"
          >
            <v-list-item-title>Option {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

  <v-navigation-drawer
      v-model="drawer"
      absolute
      temporary
    >
      <v-list
        nav
        dense
      >
        <v-list-item-group
          v-model="group"
          active-class="blue-grey lighten-1"
        >
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-castle</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Sobre Hogwarts</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-snake</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Sonserina</v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-cat</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Grifnoria</v-list-item-title>
          </v-list-item>

        <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-dog</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Lufa-Lufa</v-list-item-title>
          </v-list-item>

        <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-bird</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Corvinal</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
</div>
    
  
  
</template>

<script>
export default {
   name: 'AppTopBar',

  data: () => ({
    drawer: false,
    group: null,
}),
}
</script>