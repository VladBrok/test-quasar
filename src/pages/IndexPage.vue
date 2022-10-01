<template>
  <q-page class="q-mx-auto" style="max-width: 17rem"></q-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'IndexPage',
  data() {
    return {
      name: '',
    };
  },
  methods: {
    onSubmit() {
      console.log(this.name);
    },
  },
});
</script>
