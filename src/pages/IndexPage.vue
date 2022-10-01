<template>
  <q-page class="q-mx-auto" style="max-width: 17rem; min-height: unset">
    <h1 class="q-py-xl text-h5 text-center">
      <span v-if="answer !== 'no'"
        >Введите своё имя, и мы решим, можно ли Вам войти</span
      >
      <span v-else class="text-negative">Вход запрещен.</span>
    </h1>

    <q-form @submit="onSubmit" class="q-gutter-sm">
      <q-input
        filled
        v-model="name"
        label="Имя:"
        lazy-rules
        :rules="[(val) => (val && val.length > 0) || 'Пожалуйста, введите имя']"
      />

      <div>
        <q-btn
          :disable="isLoading"
          label="Вход"
          type="submit"
          color="primary"
          class="block q-mx-auto"
        />
      </div>
    </q-form>
  </q-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import { api } from 'boot/axios';

export default defineComponent({
  name: 'IndexPage',
  data() {
    return {
      name: '',
      answer: '',
      isLoading: false,
    };
  },
  methods: {
    async onSubmit() {
      this.isLoading = true;
      const {
        data: { answer },
      } = await api.get('');

      this.isLoading = false;
      this.answer = answer;

      if (answer === 'yes') {
        this.$router.push('/dashboard');
      }
    },
  },
});
</script>
