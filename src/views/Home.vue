<template>
  <v-container class="d-flex justify-center" fluid>
    <category-card title="Доступ пользователей" icon="mdi-account-group"></category-card>
    <category-card title="Касса" icon="mdi-cash-register"></category-card>
    <category-card title="Кредитный контроль" icon="mdi-credit-card"></category-card>
  </v-container>
</template>

<script>

  import CategoryCard from "../components/Home/CategoryCard";
  export default {
    name: 'Home',

    components: {
      CategoryCard
    },
  }
</script>
