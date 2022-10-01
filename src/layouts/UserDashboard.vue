<template>
  <div class="fullscreen text-center q-pa-md flex flex-center">
    <div>
      <div class="text-h2" style="opacity: 0.4">Добро пожаловать!</div>

      <q-btn
        class="q-mt-xl"
        color="primary"
        unelevated
        to="/"
        label="Назад"
        no-caps
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'UserDashboard',
});
</script>
