<template>
  <v-sheet class="category-card-item d-flex flex-column justify-center mr-5"
           width="200"
           height="200"
           elevation="5"
           @click="goRoute"
  >
    <v-icon size="100" color="#01579B">{{ icon }}</v-icon>
    <span class="category-title">{{ title }}</span>
  </v-sheet>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    icon: {
      type: String,
      required: true,
    },
  },
  methods: {
    goRoute() {
      this.$router.push('/categories/user-access')
    }
  }
}
</script>

<style lang="scss" scoped>
.category-card-item {
  cursor: pointer;
}
.category-title {
  font-size: 18px;
  text-align: center;
  padding: 0 10px;
}
</style>