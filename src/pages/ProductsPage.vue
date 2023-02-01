<script>
import ProductComponent from "src/components/ProductsPage/ProductComponent.vue";
import { defineComponent } from "vue";
export default defineComponent({
  components: {
    ProductComponent,
  },
  data() {
    return {
      productList: [
        { name: "Ayakkabı", amount: "50" },
        { name: "Bilgisayar", amount: "100" },
        { name: "Telefon", amount: "250" },
      ],
    };
  },
});
</script>
<template>
  <q-page>
    <ProductComponent
      v-for="item in productList"
      :key="item.name"
      :item="item"
    ></ProductComponent>
  </q-page>
</template>
