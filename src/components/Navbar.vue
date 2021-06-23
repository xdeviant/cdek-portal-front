<template>
  <v-container>
    <v-app-bar app color="primary" dark>

      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Portal</v-toolbar-title>

      <v-spacer></v-spacer>

    </v-app-bar>

    <v-navigation-drawer v-model="drawer" fixed temporary>
      <v-list>
        <v-list-item-content>
          <v-list-item-title class="title">Категорий</v-list-item-title>
        </v-list-item-content>
      </v-list>

      <v-divider></v-divider>

      <v-list>
        <v-list-item-group v-model="group">
          <v-list-item
              v-for="i in categoriesItems"
              :key="i.title"
              @click="goRoute(i.path)"
              link
          >
            {{ i.title }}
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      drawer: false,
      group: null,
      categoriesItems: [
        {
          title: 'Доступ пользователей',
          path: '/categories/user-access'
        },
        {
          title: 'Касса',
          path: '/categories/kassa'
        },
        {
          title: 'Кредитный контроль',
          path: '/categories/credit'
        },
      ]
    }
  },
  methods: {
    goRoute(path) {
      if (this.$route.path !== path) this.$router.push(path)
    }
  }
}
</script>

<style lang="scss" scoped>
.title {
  padding-left: 16px;
}
</style>