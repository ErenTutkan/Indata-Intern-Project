<template>
  <div id="counter1">
    <span style="font-size: 40px">{{ getCounter }}</span>
    <div v-if="counter < 6">
      <q-btn color="primary" label="+" @click="Increase" />
      <q-btn color="negative" label="-" @click="Deincrease" />
    </div>
  </div>
</template>
<script>
import { defineComponent } from "vue";

export default defineComponent({
  data() {
    return {
      counter: 0,
    };
  },
  methods: {
    Increase() {
      this.counter++;
    },
    Deincrease() {
      this.counter--;
    },
  },
  computed: {
    getCounter() {
      return this.counter > 5 ? "5ten Büyük" : this.counter;
    },
  },
});
</script>
