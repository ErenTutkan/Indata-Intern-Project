<template>
  <q-card class="my-card col">
    <q-card-section>
      <div class="text-h6">{{ item.name }}</div>
      <div class="text-subtitle2">{{ item.price }}</div>
    </q-card-section>
  </q-card>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    item: {
      type: Object,
    },
  },
});
</script>
