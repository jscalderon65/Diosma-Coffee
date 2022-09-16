<template>
  <div>
    <br />
    <div
      class="divider-container info-container animate__animated animate__fadeIn"
    >
      <hr class="divider-item" />
    </div>
    <div class="info-title info-container animate__animated animate__fadeIn">
      <h1>Nuestros productos</h1>
    </div>
    <div
    class="divider-container info-container animate__animated animate__fadeIn"
    >
    <hr class="divider-item" />
</div>
<br/>
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
export default {
  mounted() {},
  beforeDestroy() {},
  data() {
    return {
      imgsArr: [
        { src: "https://picsum.photos/500/300", href: "" },
        { src: "https://picsum.photos/500/600", href: "" },
        { src: "https://picsum.photos/700/300", href: "" },
        { src: "https://picsum.photos/300/800", href: "" },
        { src: "https://picsum.photos/600/800", href: "" },
        { src: "https://picsum.photos/700/300", href: "" },
        { src: "https://picsum.photos/200/300", href: "" },
        { src: "https://picsum.photos/100/200", href: "" },
        { src: "https://picsum.photos/500/800", href: "" },
        { src: "https://picsum.photos/300/800", href: "" },
        { src: "https://picsum.photos/600/800", href: "" },
        { src: "https://picsum.photos/700/300", href: "" },
        { src: "https://picsum.photos/200/300", href: "" },
        { src: "https://picsum.photos/100/200", href: "" },
        { src: "https://picsum.photos/500/800", href: "" },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
.divider-container {
  display: flex;
  justify-content: center;
}
.divider-item {
  width: 90%;
  border-radius: 10px;
  border: solid 4px;
  background:#f2e9e4 ;
}
.info-title {
  color: #f2e9e4;
  text-align: center;
  font-family: Ms madi;
  font-size: 3rem;
}
.gallery-image {
  border-radius: 10px;
  width: 100%;
  display: block;
  object-fit: cover !important;
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
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
  .info-title {
    font-size: 2rem;
  }
}
</style>
