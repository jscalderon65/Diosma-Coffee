<template>
  <div class="gallery-main-container">
    <MainTitle text="Nuestros productos" />
    <br />
    <div
      v-if="loadingGallery || imgsArr.length === 0"
      class="linear-loading-container"
    >
      <v-progress-linear
        class="linear-loading"
        indeterminate
        color="white"
      ></v-progress-linear>
      <br />
    </div>
    <div
      class="gallery-container info-container animate__animated animate__fadeIn"
      v-if="imgsArr.length > 0"
    >
      <div
        class="image-container"
        v-for="(image, index) in imgsArr"
        :key="index"
      >
        <v-img class="gallery-image" :src="image.serverUrl" />
      </div>
    </div>
  </div>
</template>

<script>
import MainTitle from "./mainTitle.vue";
export default {
  components: { MainTitle },
  mounted() {},
  beforeDestroy() {},
  data() {
    return {
      imgsArr: [],
      loadingGallery: false,
    };
  },
  created() {
    this.getImages();
  },
  methods: {
    async getGalleryData() {
      const response = await this.$fire.firestore
        .collection("Gallery")
        .doc("Images")
        .get();
      return response.data().data;
    },
    async getImages() {
      try {
        this.loadingGallery = true;
        this.imgsArr = await this.getGalleryData();
        this.loadingGallery = false;
      } catch (error) {
        this.loadingGallery = false;
        console.log(error);
      }
    },
  },
};
</script>

<style scoped>
.gallery-image {
  border-radius: 10px;
  width: 100%;
  display: block;
  object-fit: cover !important;
  box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
}
.gallery-container {
  width: 90vw;
  margin: auto;
  margin-bottom: 20px;
  column-count: 4;
  column-gap: 10px;
}
.linear-loading-container {
  width: 100%;
  display: flex;
  justify-content: center;
}
.linear-loading {
  width: 90%;
}
.image-container {
  margin: 0;
  display: grid;
  grid-template-rows: 1fr auto;
  margin-bottom: 10px;
  break-inside: avoid;
}
.gallery-image:hover {
  cursor: pointer;
}
.image-container > .gallery-image {
  grid-row: 1 / -1;
  grid-column: 1;
}

@media (max-width: 600px) {
  .gallery-container {
    column-count: 2;
    column-gap: 10px;
  }
}
</style>
