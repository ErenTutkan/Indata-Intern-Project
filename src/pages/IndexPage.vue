<template>
  <q-page class="flex flex-center">
    <q-btn to="/counter" label="Counter Page"></q-btn>
    <q-btn to="/products" label="Products Page"></q-btn>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage'
})
</script>
