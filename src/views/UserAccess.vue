<template>
  <v-row class="justify-center">

    <v-col cols="12">
      <h1 class="text-center">Доступ пользователей</h1>
    </v-col>

    <v-col cols="2">
      <div class="d-flex justify-center">
        <v-btn color="accent" @click="addForm">Добавить форму</v-btn>
      </div>
    </v-col>

    <template>
      <v-col cols="12">
        <div class="d-flex flex-column align-center">
          <user-access-form
              v-for="(form, idx) in forms"
              :form-data="form"
              :key="idx"
          />
        </div>
      </v-col>
    </template>

  </v-row>
</template>

<script>
import UserAccessForm from "../components/UserAccess/UserAccessForm";

export default {
  components: {UserAccessForm},
  data() {
    return {
      test: null,
      forms: [],
    }
  },
  created() {
    this.addForm()
  },
  methods: {
    addForm() {
      const newForm = {
        subdivision: '',
        employee: '',
        reason: '',
        adBlock: false,
      }

      this.forms.push(newForm);
    }
  }
}
</script>