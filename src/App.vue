<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      app
    >
      <v-list dense>
        <v-list-item 
          v-for="item in menu"
          :key="item.opcoes"
          link
          router
          :to="item.rota">
          <v-list-item-action>
            <v-icon>{{item.icone}}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{item.titulo}}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      color="black"
      dark
      height="100px"
    >
    <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-row>
        <v-col class="text-center">
          <v-toolbar-title>Weekly Planner</v-toolbar-title>
        </v-col>
      </v-row>
    </v-app-bar>
    <v-main class="ma-3" app>
      <router-view></router-view>
    </v-main>
    <v-footer
      color="black"
      app
    >
      <span class="white--text">&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    props: {
      source: String,
    },
    name: "App",
    data: () => ({
      drawer: null,
      menu:[
        {
          titulo: "Calendário",
          icone:"mdi-calendar-multiple",
          rota:"/Calendar",
        },
        {
          titulo:"Tarefas",
          icone:"mdi-file-outline",
          rota:"",
        }
      ]
    }),
  }
</script>