<template>
  <div class="menu-container">
    <br />
    <br />
    <div
      class="divider-container info-container animate__animated animate__fadeIn"
    >
      <hr class="divider-item" />
    </div>
    <div class="info-title info-container animate__animated animate__fadeIn">
      <h1>Menú</h1>
    </div>
    <div
      class="divider-container info-container animate__animated animate__fadeIn"
    >
      <br />
      <hr class="divider-item" />
    </div>
    <div
      class="category-container"
      style="margin-top: 20px; margin-bottom: 50px"
      v-for="(category, index) in categories"
      :key="index"
    >
      <div>
        <div>
          <div
            class="title-category info-container animate__animated animate__fadeIn"
          >
            <h2 class="decorated title-category">
              <span>{{ category.name }}</span>
            </h2>
          </div>
        </div>
        <div
          style="
            display: grid;
            grid-gap: 10px;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            grid-auto-rows: 1fr;
            justify-items: center;
            padding-top: 20px;
            padding-bottom: 20px;
          "
        >
          <div
            v-for="(product, indexProduct) in category.items"
            :key="indexProduct"
            style="
              display: flex;
              justify-content: center;
              align-items: center;
              width: 160px;
              height: auto;
              padding-bottom: 10px;
              padding-top: 10px;
              border-radius: 10px;
              flex-flow: column;
            "
          >
            <v-img
              style="
                text-align: center;
                width: 160px;
                height: 160px;
                border-radius: 100%;s
              "
              :key="indexProduct"
              class="gallery-image"
              :src="product.src"
              lazy-src="https://picsum.photos/500/600"
            />
            <br />
            <div style="border-radius: 10px; text-align: center; width: 100%">
              <b style="font-family: Ms Madi; font-size: 1.5rem">{{
                product.info.name
              }}</b>
              <br />
              <b>{{ product.info.price }}</b>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div style="text-align: center">
      <button class="main-button menu-button">
        <a href="/menu">¡Recomiendame algo!</a>
      </button>
    </div>
    <br />
    <br />
  </div>
</template>

<script>
export default {
  mounted() {},
  beforeDestroy() {},
  data() {
    return {
      categories: [
        {
          name: "Café",
          items: [
            {
              src: "https://picsum.photos/500/300",
              info: {
                name: "Café",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/500/300",
              info: {
                name: "Café",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/500/600",
              info: {
                name: "Café",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/700/300",
              info: {
                name: "Café",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/300/800",
              info: {
                name: "Café",
                price: "20.000",
              },
            },
          ],
        },
        {
          name: "Alimentos",
          items: [
            {
              src: "https://picsum.photos/500/300",
              info: {
                name: "Alimentos",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/500/600",
              info: {
                name: "Alimentos",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/700/300",
              info: {
                name: "Alimentos",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/300/800",
              info: {
                name: "Alimentos",
                price: "20.000",
              },
            },
          ],
        },
        {
          name: "Licores",
          items: [
            {
              src: "https://picsum.photos/500/300",
              info: {
                name: "Licores",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/500/600",
              info: {
                name: "Licores",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/700/300",
              info: {
                name: "Licores",
                price: "20.000",
              },
            },
            {
              src: "https://picsum.photos/300/800",
              info: {
                name: "Licores",
                price: "20.000",
              },
            },
          ],
        },
      ],
    };
  },
  methods: {},
};
</script>

<style>
.main-button.menu-button {
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  width: 50%;
  font-family: "Permanent Marker";
  font-size: 1.5rem;
  padding: 7px 20px !important;
  border-radius: 5px;
  margin: 0px 0px 0px 20px;
  background-color: rgba(255, 255, 255, 0);
  border: 6px solid #f2e9e4;
  transition: 0.8s;
}

.main-button.menu-button a {
  text-decoration: none;
  color: #f2e9e4;
}

.main-button.menu-button:hover {
  background-color: black;
  cursor: pointer;
}
.main-button.menu-button:hover a {
  color: #f2e9e4;
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
}
</style>
