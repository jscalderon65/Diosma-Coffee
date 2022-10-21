<template>
  <div class="menu-container">
    <MainTitle text="Menú" />
    <div v-if="loadingData || products.length === 0">
      <br />
      <v-progress-linear indeterminate color="white"></v-progress-linear>
    </div>
    <div
      class="category-main-container"
      v-for="(category, index) in products"
      :key="index"
    >
      <div>
        <div>
          <div
            class="title-category info-container animate__animated animate__fadeIn"
          >
            <h2 class="decorated title-category">
              <span>{{ category.section }}</span>
            </h2>
          </div>
        </div>
        <div class="category-grid-container">
          <div
            v-for="(product, indexProduct) in category.products"
            :key="indexProduct"
            class="card-category-container"
          >
            <v-img
              class="product-card-image"
              :key="indexProduct"
              :src="product.imageUrl"
              lazy-src="https://picsum.photos/500/600"
            />
            <br />
            <div class="card-category-text">
              <b class="card-category-name">{{ product.name }}</b>
              <br />
              <b>{{
                new Intl.NumberFormat("en", {
                  style: "currency",
                  currency: "COP",
                  maximumFractionDigits: 0,
                }).format(product.price)
              }}</b>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="suggestion-container">
      <v-btn
        v-if="!loadingData || products.length > 0"
        @click="openSuggestionDialog"
        class="suggestion-btn"
        outlined
      >
        <v-icon style="margin-right: 10px">mdi-wallet-giftcard</v-icon>
        Recomiendame algo</v-btn
      >
    </div>
    <v-dialog v-model="dialog" width="500">
      <v-card>
        <v-card-title class="share-modal-title">
          <h1>¡Mira lo que te recomiendo hoy!</h1>
        </v-card-title>
        <br />
        <v-card-text v-if="suggestionProduct" class="dialog-suggestion-text">
          <div class="card-category-container">
            <v-img
              class="product-card-image"
              :src="suggestionProduct.imageUrl"
            />
            <br />
            <div class="card-category-text">
              <b class="card-category-name">{{ suggestionProduct.name }}</b>
              <br />
              <b>{{
                new Intl.NumberFormat("en", {
                  style: "currency",
                  currency: "COP",
                  maximumFractionDigits: 0,
                }).format(suggestionProduct.price)
              }}</b>
            </div>
          </div>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn @click="closeDialog"> Cerrar </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <br />
    <br />
  </div>
</template>

<script>
import MainTitle from "~/components/mainTitle.vue";
import MainButton from "~/components/mainButton.vue";
export default {
  components: { MainButton, MainTitle },
  data() {
    return {
      products: [],
      loadingData: false,
      dialog: false,
      suggestionProduct: null,
    };
  },
  created() {
    this.getProducts();
  },
  methods: {
    async getProductsData() {
      const response = await this.$fire.firestore
        .collection("Products")
        .doc("Menu")
        .get();
      return response.data().data;
    },
    async getProducts() {
      try {
        this.loadingData = true;
        this.products = await this.getProductsData();
        this.loadingData = false;
      } catch (error) {
        console.log(error);
        console.log(error);
        this.loadingData = false;
      }
    },
    randomNumber(min, max) {
      return Math.floor(Math.random() * (max - min + 1) + min);
    },
    openSuggestionDialog() {
      const categoryLength = this.products.length;
      const randomCategory = this.randomNumber(0, categoryLength - 1);
      const productLength = this.products[randomCategory].products.length;
      const randomProduct = this.randomNumber(0, productLength - 1);
      this.suggestionProduct =
        this.products[randomCategory].products[randomProduct];
      this.dialog = true;
    },
    closeDialog() {
      this.dialog = false;
    },
  },
};
</script>

<style>
.dialog-suggestion-text {
  display: flex;
  justify-content: center;
}
.suggestion-btn {
  font-family: Permanent Marker;
  font-size: 1.2rem;
  margin: autos;
}
.suggestion-container {
  display: flex;
  justify-content: center;
}
.share-modal-title {
  text-align: center;
  font-family: Ms madi !important;
  display: flex;
  justify-content: center;
  width: 100%;
}
.card-category-name {
  font-family: Ms Madi;
  font-size: 1.5rem;
}
.card-category-text {
  border-radius: 10px;
  text-align: center;
  width: 100%;
}
.product-card-image {
  text-align: center;
  width: 160px;
  height: 160px;
  border-radius: 100%;
}
.category-main-container {
  margin-top: 20px;
  margin-bottom: 50px;
}
.category-grid-container {
  display: grid;
  grid-gap: 10px;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  grid-auto-rows: 1fr;
  justify-items: center;
  padding-top: 20px;
  padding-bottom: 20px;
}
.card-category-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 160px;
  height: auto;
  padding-bottom: 10px;
  padding-top: 10px;
  border-radius: 10px;
  flex-flow: column;
}
.product-card {
  border: solid;
  width: 60%;
}
.menu-container {
  padding: 20px;
}
.divider-container {
  display: flex;
  justify-content: center;
}
.divider-item {
  width: 90%;
  border-radius: 10px;
  border: solid 4px;
  background: #f2e9e4;
}
.info-title {
  color: #f2e9e4;
  text-align: center;
  font-family: Ms madi;
  font-size: 3rem;
}
.title-category {
  color: #f2e9e4;
  font-family: Ms madi;
  font-size: 3rem;
}
.decorated {
  overflow: hidden;
  text-align: center;
}
.decorated > span {
  position: relative;
  display: inline-block;
}
.decorated > span:before,
.decorated > span:after {
  content: "";
  position: absolute;
  top: 50%;
  border-bottom: 2px solid;
  width: 100vw;
  margin: 0 20px;
  border: solid;
  border-radius: 10px;
}
.decorated > span:before {
  right: 100%;
}
.decorated > span:after {
  left: 100%;
}
.menu-container {
  min-height: 100vh;
  height: auto;
}
@media (max-width: 600px) {
  .title-category {
    text-align: center;
  }
  .main-button.menu-button {
    font-size: 1rem;
  }
}
</style>
