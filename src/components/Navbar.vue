<template>
  <nav>
    <v-navigation-drawer v-model="drawer" app fixed class="primary">
      <v-col>
        <v-row justify="center" class="mt-5">
          <v-avatar size="100">
            <img src="sf7.jpg" />
          </v-avatar>
        </v-row>
        <v-row justify="center">
          <p class="white--text subheading mt-1">Kenan Erarslan</p>
        </v-row>
        <v-row justify="center" class="mt-4 mb-3">
          <Popup/>
        </v-row>
      </v-col>
      <v-list>
        <v-list-item-group>
          <v-list-item v-for="link in links" :key="link.text" router :to="link.route">
            <v-list-item-icon>
              <v-icon v-text="link.icon" class="white--text"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title class="white--text">{{ link.text }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon color="grey" class="grey--text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title class="grey--text">
        <span class="font-weight-light">Enginaar</span>
        <span class="font-weight-dark text-uppercase">Todo</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-menu offset-y>
        <template v-slot:activator="{ on }">
          <v-btn color="grey" text v-on="on">Menu</v-btn>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in links" :key="index" router :to="item.route">
            <v-list-item-title  >{{ item.text }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-btn text color="grey">
        <span>Sign Out</span>
        <v-icon right>mdi-exit-to-app</v-icon>
      </v-btn>
    </v-app-bar>
  </nav>
</template>

<script>
import Popup from './Popup.vue'
export default {
  components: {Popup},
  data() {
    return {
      drawer: false,
      links: [
        { icon: "mdi-view-dashboard", text: "Dashboard", route: "/" },
        { icon: "mdi-folder", text: "My Projects", route: "/projects" },
        { icon: "mdi-account", text: "Team", route: "/team" }
      ]
    };
  }
};
</script>