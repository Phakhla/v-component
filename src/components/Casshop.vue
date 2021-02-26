<template>
  <div class="row">
    <div
      class="card"
      style="width: 15rem"
      v-for="item in products"
      :key="item.id"
    >
      <img :src="item.imgUrl" class="card-img-top" :alt="item.title" />
      <div class="card-body">
        <p class="card-title">{{ item.title }}</p>
        <p class="card-text">{{ item.price.toLocaleString() }} บาท</p>
        <button class="btn btn-dark" @click="addItemToCart(item)">
          หยิบใส่ตะกร้า
        </button>
        
      </div>
    </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
export default {
  name: "Casshop",
  mounted() {
    this.getProducts();
  },
  computed: {
    ...mapGetters(["products"]),
  },
  methods: {
    ...mapActions(["addItemToCart", "getProducts"]),
  },
};
</script>

<style scoped>
.card {
  padding: 20px;
  border: none;
}
</style>