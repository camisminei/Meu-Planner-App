<template>
  <div id="app">
    <v-app>
      <v-app-bar app color="white" height="100">
        <v-avatar class="mr-3" color="grey lighten-5" size="70">
          <v-img contain max-height="70%" src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png">
          </v-img>
        </v-avatar>

        <v-toolbar-title class="font-weight-black headline">
          VUETIFY
        </v-toolbar-title>
      </v-app-bar>

      <v-content>
        <section id="hero">
          <v-row no-gutters>
            <v-img
            :min-height="'calc(100vh - '+ $vuetify.application.top + 'px)'"
            src="https://images.unsplash.com/photo-1581309638082-877cb8132535?ixlib=rb-1.2.1&auto=format&fit=crop&w=1500&q=80"
            >
              <v-theme-provider dark>
                <v-container fill-height>
                  <v-row
                  align="center"
                  class="white--text mx-auto"
                  justify="center">

                    <v-col
                    class="white--text text-center"
                    cols="12"
                    tag="h1">
                      <span
                        :class="[$vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2']"
                        class="font-weight-light"
                      >
                        WELCOME TO
                      </span>

                      <br>

                      <span
                        :class="[$vuetify.breakpoint.smAndDown ? 'display-3': 'display-4']"
                        class="font-weight-black"
                      >
                        VUETIFY
                      </span>
                    </v-col>
                      <v-btn
                      class="align-self-end"
                      fab
                      outlined
                      @click="$vuetify.goTo('#about-me')"
                    >
                      <v-icon>mdi-chevron-double-down</v-icon>
                    </v-btn>
                  </v-row>
                </v-container>
              </v-theme-provider>
            </v-img>
          </v-row>
        </section>
        <section id="about-me">
          <div class="py-12"></div>

          <v-container class="text-center">
            <h2 class="display-2 font-weight-bold mb-3">ABOUT ME</h2>
            <v-responsive
              class="mx-auto mb-8"
              width="56">
              <v-divider class="mb-1"></v-divider>
              <v-divider></v-divider>
            </v-responsive>

          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="720"
          >
            Vuetify is the #1 component library for Vue.js and has been in active development since 2016. The goal of the project is to provide users with everything that is needed to build rich and engaging web applications using the Material Design specification. It accomplishes that with a consistent update cycle, Long-term Support (LTS) for previous versions, responsive community engagement, a vast ecosystem of resources and a dedication to quality components.
          </v-responsive>
          <v-avatar
            class="elevation-12 mb-12"
            size="128"
          >
            <v-img src="https://image.flaticon.com/icons/svg/172/172163.svg"></v-img>
          </v-avatar>
          <div></div>
          <v-btn
            color="grey"
            href="https://vuetifyjs.com"
            outlined
            large
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              Vuetify Documentation
            </span>
          </v-btn>

          <div class="py-12"></div>
          </v-container>
        </section>

        <section id="stats">
          <v-parallax
          :height="$vuetify.breakpoint.smAndDown ? 700 : 500"
          src="https://images.unsplash.com/photo-1510915228340-29c85a43dcfe?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80">
            <v-container fill-height>
            <v-row class="mx-auto">
              <v-col
                v-for="[value, title] of stats"
                :key="title"
                cols="12"
                md="3"
              >
                <div class="text-center">
                  <div
                    class="display-3 font-weight-black mb-4"
                    v-text="value"
                  ></div>

                  <div
                    class="title font-weight-regular text-uppercase"
                    v-text="title"
                  ></div>
                </div>
              </v-col>
            </v-row>
          </v-container>
          </v-parallax>
        </section>
        <section id="about-me2">
          <div class="py-12"></div>

          <v-container class="text-center">
            <h2 class="display-2 font-weight-bold mb-3">ABOUT ME</h2>
            <v-responsive
              class="mx-auto mb-8"
              width="56">
              <v-divider class="mb-1"></v-divider>
              <v-divider></v-divider>
            </v-responsive>

          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="720"
          >
            Vuetify is the #1 component library for Vue.js and has been in active development since 2016. The goal of the project is to provide users with everything that is needed to build rich and engaging web applications using the Material Design specification. It accomplishes that with a consistent update cycle, Long-term Support (LTS) for previous versions, responsive community engagement, a vast ecosystem of resources and a dedication to quality components.
          </v-responsive>
          <v-avatar
            class="elevation-12 mb-12"
            size="128"
          >
            <v-img src="https://image.flaticon.com/icons/svg/172/172163.svg"></v-img>
          </v-avatar>
          <div></div>
          <v-btn
            color="grey"
            href="https://vuetifyjs.com"
            outlined
            large
          >
            <span class="grey--text text--darken-1 font-weight-bold">
              Vuetify Documentation
            </span>
          </v-btn>

          <div class="py-12"></div>
          </v-container>
        </section>
      </v-content>
    </v-app>
  </div>
</template>

<script>
export default {
  props:{
    source:String,
  },
  name:"App",
  data: ()=>({
    stats:[
      ['24k', 'Github Stars'],
      ['330+', 'Releases'],
      ['1m', 'Downloads/mo'],
      ['5m', 'Total Downloads'],
    ]
  })
}
</script>