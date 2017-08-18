<template>
  <v-app light>
    <v-navigation-drawer
      persistent
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
    >
      <v-list>
        <v-list-tile 
          v-for="(item, i) in items"
          :key="i"
          value="true"
        >
          <v-list-tile-action>
            <v-icon light v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar fixed>
      <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-btn 
        icon
        @click.native.stop="miniVariant = !miniVariant"
      >
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-btn
        icon
        @click.native.stop="clipped = !clipped"
      >
        <v-icon>web</v-icon>
      </v-btn>
      <v-btn
        icon
        @click.native.stop="fixed = !fixed"
      >
        <v-icon>remove</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        icon
        @click.native.stop="rightDrawer = !rightDrawer"
      >
        <v-icon>menu</v-icon>
      </v-btn>
    </v-toolbar>
    <main>
      <v-container fluid>
        <v-slide-y-transition mode="out-in">
          <v-layout rows align-center wrap>
            img tag absolute import by using src="/public/v.png" <img src="/public/v.png" alt="Vuetify.js" class="mb-5" />
            img tag relative import by using src="./v.png" <img src="./v.png" alt="Vuetify.js" class="mb-5" />

            <v-card>
              <v-card-media src="/public/v.png" height="200px">
              </v-card-media>
              <v-card-title primary-title>
                <div>
                  <div>v-card-media absolute import by using src="/public/v.png"</div>
                </div>
              </v-card-title>
              <v-card-actions>
                <v-btn flat class="orange--text">Share</v-btn>
                <v-btn flat class="orange--text">Explore</v-btn>
              </v-card-actions>
            </v-card>

            <v-card>
              <v-card-media src="./v.png" height="200px">
              </v-card-media>
              <v-card-title primary-title>
                <div>
                  <div>v-card-media relative import by using src="./v.png"</div>
                </div>
              </v-card-title>
              <v-card-actions>
                <v-btn flat class="orange--text">Share</v-btn>
                <v-btn flat class="orange--text">Explore</v-btn>
              </v-card-actions>
            </v-card>

            <v-card>
              <v-card-media v-bind:src="require('./v.png')" height="200px">
              </v-card-media>
              <v-card-title primary-title>
                <div>
                  <div>v-card-media relative import by using v-bind:src="require('./v.png')"</div>
                </div>
              </v-card-title>
              <v-card-actions>
                <v-btn flat class="orange--text">Share</v-btn>
                <v-btn flat class="orange--text">Explore</v-btn>
              </v-card-actions>
            </v-card>
          </v-layout>
        </v-slide-y-transition>
      </v-container>
    </main>
    <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon light>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-footer :fixed="fixed">
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        clipped: false,
        drawer: true,
        fixed: false,
        items: [
          { icon: 'bubble_chart', title: 'Inspire' }
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false,
        title: 'Vuetify.js'
      }
    }
  }
</script>

<style lang="stylus">
  @import './stylus/main'
</style>
