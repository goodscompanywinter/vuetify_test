<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-spacer></v-spacer>

    </v-app-bar>

    <template>
      <v-card
          height="400"
          width="256"
          class="mx-auto"
      >
        <v-navigation-drawer v-model="drawer" app>
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title class="text-h6">
                Application
              </v-list-item-title>
              <v-list-item-subtitle>
                subtext
              </v-list-item-subtitle>
            </v-list-item-content>
          </v-list-item>

          <v-divider></v-divider>

          <v-list
              dense
              nav
          >
            <v-list-item
                v-for="item in items"
                :key="item.title"
                link
                :to="item.to"
            >
              <v-list-item-icon>
                <v-icon>{{ item.icon }}</v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-navigation-drawer>
      </v-card>
    </template>

    <v-main>
      <v-container class="red" fluid>
        <router-view/>
      </v-container>

    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    drawer: false,
    items: [
      { title: 'Dashboard', icon: 'mdi-view-dashboard', to: '/' },
      { title: 'GridSystem', icon: 'mdi-image', to: '/grid-system' },
      { title: 'GridListPage', icon: 'mdi-image', to: '/grid-list-page' },
    ],
    right: null,
  }),
};
</script>
