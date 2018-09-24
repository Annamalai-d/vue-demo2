<template>
  <v-container>
    <v-navigation-drawer
        fixed
        :mini-variant="miniVariant"
        :clipped="clipped"
        v-model="drawer"
        app
      >
        <v-list>
          <template v-for="(item,index) in items">
            <v-list-tile>
            <v-btn icon>
              <v-icon>{{item.icon}}</v-icon>
            </v-btn>
            <v-list-tile-title>{{item.title}}</v-list-tile-title>
            </v-list-tile>
          </template>
        </v-list>
      </v-navigation-drawer>
      <v-toolbar fixed app :clipped-left="clipped">
        <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
        <v-btn 
          icon
          @click.stop="miniVariant = !miniVariant"
        >
          <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
        </v-btn>
        <v-toolbar-title v-text="title"></v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn flat color="primary" v-if="!isUser"
          @click.native.stop="rightDrawer = !rightDrawer"
        >Login
        </v-btn>
      </v-toolbar>
  </v-container>
</template>
<script>
export default {
  data () {
    return {
       clipped: true,
        drawer: true,
        fixed: false,
        title: 'Home',
        isUser: false,
        items: [
          { icon: 'home', title: 'Home' },
          { icon: 'open_folder', title: 'Videos'},
          { icon: 'open_folder', title: 'Videos'}
        ],
        miniVariant: false,
        right: true,
        rightDrawer: false
    }
  },
  created() {
      if (screen.width < 400) {
        this.miniVariant = true;
      }
  }
}
</script>

