<template>
  <div class="gallery-main-container">
    <MainTitle text="Nuestros productos" />
    <br />
    <div
      class="gallery-container info-container animate__animated animate__fadeIn"
    >
      <div
        class="image-container"
        v-for="(image, index) in imgsArr"
        :key="index"
      >
        <v-img
          class="gallery-image"
          :src="image.src"
          lazy-src="https://picsum.photos/500/600"
        />
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
      imgsArr: [
        {
          src: "https://lh5.googleusercontent.com/p/AF1QipMnovizSdDk33mFeq9IeTSp5f1KJzGUjfo4RJ44=w660-h1087-p-k-no",
          href: "",
        },
        {
          src: "https://lh5.googleusercontent.com/p/AF1QipOFfds77pt9e11V0kFz-fAe7yzdM9pvD30wRI7U=w660-h1087-p-k-no",
          href: "",
        },
        {
          src: "https://lh5.googleusercontent.com/p/AF1QipOFfds77pt9e11V0kFz-fAe7yzdM9pvD30wRI7U=w660-h1087-p-k-no",
          href: "",
        },
        {
          src: "https://lh5.googleusercontent.com/p/AF1QipPmvjvj6Sdf7N7vXUPh3rC1Ih4jeBnS7hMNClpl=w660-h353-p-k-no",
          href: "",
        },
        {
          src: "https://lh5.googleusercontent.com/p/AF1QipOEp0tTSaideLWudUwo5Dkn6urbDTbfm1gCQC3_=w660-h1087-p-k-no",
          href: "",
        },
        {
          src: "https://lh5.googleusercontent.com/p/AF1QipOdqOQWjD8ZaMQgdYlgLaodrKeDMZfgZVizhHeM=w660-h1087-p-k-no",
          href: "",
        },
        {
          src: "https://lh5.googleusercontent.com/p/AF1QipPdwUUt-OVwJK4xvJ7KgWA3sd7ADuy8J80G7q8m=w660-h1087-p-k-no",
          href: "",
        },
      ],
    };
  },
  methods: {},
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
