<template>
  <div class="cart">
    <h3 class="text-white h3">
      <span class="badge badge-light">
        <a class="navbar-brand" href="#"
          >{{ totalQty }}
          <img
            src="https://img.favpng.com/12/18/15/shopping-cart-icon-png-favpng-e5DiMUYLNYaTjdsibphFUCAxC.jpg"
            width="30"
            height="30"
            alt=""
            loading="lazy"
          /> </a
      ></span>
    </h3>

    <div
      v-if="orderPlaced"
      @click="() => (this.orderPlaced = false)"
      class="alert alert-success alert-dismissible fade show"
      role="alert"
    >
      ทำรายการสำเร็จ!
      <button
        type="button"
        class="close"
        data-dismiss="alert"
        aria-label="Close"
      >
        <span aria-hidden="true">&times;</span>
      </button>
    </div>
    <ul class="list-group">
      <li class="list-group-item" v-for="item in cart" :key="item.id">
        <button
          @click="removeItemFromCart(item.id)"
          type="button"
          class="close"
          data-dismiss="modal"
          aria-label="Close"
        >
          <span aria-hidden="true">&times;</span>
        </button>
        <div class="media">
          <img width="80px" :src="item.imgUrl" class="mr-3" alt="item.title" />
          <div class="media-body">
            <p class="mt-0">{{ item.title }}</p>
            <button
              class="qty-button btn btn-sm btn-secondary"
              @click="reduceQty(item.id)"
            >
              -
            </button>
            x {{ item.qty }}
            <button
              class="qty-button btn btn-sm btn-secondary"
              @click="addQty(item.id)"
            >
              +
            </button>
            = {{ item.price * item.qty }} 
          </div>
        </div>
      </li>
    </ul>
    <button
      v-if="cart.length"
      @click="placeOrder"
      class="checkout-button btn btn-lg btn-block btn-success"
      :disabled="isProcessing"
    >
      <div v-if="isProcessing" class="spinner-border" role="status">
        <span class="sr-only">Loading...</span>
      </div>
      <span v-else>ราคารวม = {{ totalPrice.toLocaleString() }} บาท</span>
    </button>
  </div>
</template>
<script>
import { mapGetters, mapActions } from "vuex";
export default {
  name: "Cart",

  data() {
    return {
      isProcessing: false,
      orderPlaced: false,
    };
  },
  computed: {
    ...mapGetters(["cart"]),
    totalPrice() {
      return this.cart.reduce((a, b) => a + b.qty * b.price, 0);
    },
    totalQty() {
      return this.cart.reduce((a, b) => a + b.qty, 0);
    },
  },
  methods: {
    ...mapActions(["removeItemFromCart", "addQty", "reduceQty", "emptyCart"]),
    placeOrder() {
      this.isProcessing = true;
      setTimeout(() => {
        this.isProcessing = false;
        this.orderPlaced = true;
        this.emptyCart();
      }, 1000);
    },
  },
};
</script>

<style scoped>
.media {
  width: 90%;
  text-align: left;
}
.qty-button {
  border-radius: 50%;
  width: 30px;
}
.checkout-button {
  margin-top: 20px;
}
</style>