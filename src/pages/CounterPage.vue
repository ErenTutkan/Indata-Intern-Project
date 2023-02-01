<template>
  <q-page>
    <div class="row">
      <CounterComponent v-for="item in 10" :key="item"></CounterComponent>
    </div>
  </q-page>
</template>
<script>
import { defineComponent } from "vue";
import CounterComponent from "src/components/CounterPage/CounterComponent.vue";
export default defineComponent({
  components: {
    CounterComponent,
  },
});
</script>
