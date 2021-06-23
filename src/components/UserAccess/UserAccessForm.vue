<template>
  <v-sheet class="user-access mb-5" width="800" elevation="5">
    <v-form>
      <v-container>
        <v-row class="d-flex justify-center">
          <v-col cols="10">
            <v-autocomplete placeholder="Подразделение"></v-autocomplete>
          </v-col>
          <v-col cols="10">
            <v-autocomplete placeholder="Сотрудник"></v-autocomplete>
          </v-col>
          <v-col cols="10">
            <v-select
                :items="items"
                placeholder="Причина блокировки"
            ></v-select>
          </v-col>
          <v-col cols="10">
            <v-checkbox
                v-model="checkbox"
                label="Блокировать AD"
            ></v-checkbox>
          </v-col>
          <v-col cols="5">
            <v-btn color="secondary"
                   elevation="2"
                   rounded
                   @click="goHome"
            >Назад
            </v-btn>
          </v-col>
          <v-col cols="5" class="d-flex justify-end">
            <v-btn color="primary"
                   elevation="2"
                   rounded
            >Отправить
            </v-btn>
          </v-col>
        </v-row>
      </v-container>
    </v-form>
  </v-sheet>
</template>

<script>
export default {
  props: {
    formData: {
      type: Object,
      required: true,
    }
  },
  data() {
    return {
      form: this.formData,
      items: ['1', '2', '3', '4', '5'],
      checkbox: false,
    }
  },
  methods: {
    goHome() {
      this.$router.push('/');
    }
  }
}
</script>

<style lang="scss" scoped>

</style>