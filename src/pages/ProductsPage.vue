<template>
  <q-page class="q-pa-md">
    <div class="row items-center q-col-gutter-md">
      <div class="col-4 col-md-5">
        <q-input label="Name" v-model="newProductName"></q-input>
      </div>
      <div class="col-4 col-md-5">
        <q-input
          label="Price"
          type="number"
          v-model="newProductPrice"
        ></q-input>
      </div>
      <div class="col-4 col-md-2">
        <q-btn
          label="Add Product"
          @click="addProduct"
          color="primary"
          icon="add"
        ></q-btn>
      </div>
    </div>

    <div class="col q-mt-md">
      <div class="column q-col-gutter-md">
        <div class="col" v-for="item in productList" :key="item.name">
          <ProductComponent
            :item="item"
            @deleteItem="deleteItem"
          ></ProductComponent>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import ProductComponent from "src/components/ProductsPage/ProductComponent.vue";
import { defineComponent, ref } from "vue";

export default defineComponent({
  components: {
    ProductComponent,
  },
  setup() {
    const productList = ref([
      { id: "asdashfhaf", name: "Ayakkabı", price: "50" },
      { id: "adfhasdhads", name: "Bilgisayar", price: "100" },
      { id: "afasfhasfhd", name: "Telefon", price: "250" },
    ]);
    const deleteItem = (id) => {
      productList.value = productList.value.filter((item) => item.id !== id);
    };
    const newProductName = ref("");
    const newProductPrice = ref("");
    return {
      productList,
      deleteItem,
      newProductName,
      newProductPrice,

      addProduct() {
        const name = newProductName.value;
        const price = newProductPrice.value;

        if (!name || !price) {
          return;
        }

        const newProduct = {
          name,
          price,
        };

        productList.value.push(newProduct);

        newProductName.value = "";
        newProductPrice.value = "";
      },
    };
  },
});
</script>
