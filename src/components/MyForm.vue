<script lang="ts">

import { ref, onMounted } from "vue";

export default {
  setup() {
    const name = ref('')
    const el = ref()

    const submitForm = () => {
      console.log(`Form submitted! Name = ${name.value}`)
    }

    onMounted(() => {
      el.value.focus()
    });

    return {
      el,
      name,
      submitForm
    }
  }
};
</script>

<template>
  <div>
    <p>{{ name }}</p>
    <input ref="el" type="text" placeholder="name" v-model="name" />
    <div>
      <button @click="submitForm" :disabled="name.length == 0">Submit</button>
    </div>
  </div>
</template>

<style scoped>

  input[type='text'] {
    padding: 5px;
  }

  button {
    margin-top: 20px;
  }
</style>
