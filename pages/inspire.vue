<template>
  <div class="about-container animate__animated animate__fadeIn">
    <MainTitle text="Conoce un poco de nosotros" />
    <br />
    <div class="text-body-container">
      <div>
        <v-img
          class="image-about-us"
          src="https://picsum.photos/500/600"
          lazy-src="https://picsum.photos/200/300/?blur=10"
        />
      </div>
      <br />
      <div class="about-us-container-text">
        <h1 class="about-subtitle">¿Quienes somos?</h1>
        <br />
        <div class="list-">
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. A, suscipit
            voluptate dolores quos placeat laudantium eaque ut tempore delectus
            blanditiis id ratione quam impedit architecto, dolore nobis?
            Quisquam, voluptates vero. Lorem ipsum dolor sit amet consectetur
            adipisicing elit. A, suscipit voluptate dolores quos placeat
            laudantium eaque ut tempore delectus blanditiis id ratione quam
            impedit architecto, dolore nobis? Quisquam, voluptates vero.
            Quisquam, voluptates vero. Lorem ipsum dolor sit amet consectetur
            adipisicing elit. A, suscipit voluptate dolores quos placeat
            laudantium eaque ut tempore delectus blanditiis id ratione quam
            impedit architecto, dolore nobis? Quisquam, voluptates vero.
          </p>
        </div>
      </div>
      <br />
      <div class="our-history">
        <h1 class="about-subtitle">Nuestra historia</h1>
        <br />
        <div class="about-list-body-text">
          <v-timeline :reverse="reverse" :dense="$vuetify.breakpoint.smAndDown">
            <v-timeline-item v-for="n in 4" :key="n" color="white">
              <span class="about-list-date" slot="opposite">202{{ n }}</span>
              <v-card class="elevation-2">
                <v-card-title class="about-list-title">
                  Lorem ipsum
                </v-card-title>
                <v-card-text>
                  Lorem ipsum dolor sit amet, no nam oblique veritus. Commune
                  scaevola imperdiet nec ut, sed euismod convenire principes at.
                  Est et nobis iisque percipit, an vim zril disputando
                  voluptatibus, vix an salutandi sententiae.
                </v-card-text>
                <div class="about-list-image-container">
                  <div>
                    <v-img
                      class="about-list-image-body"
                      src="https://picsum.photos/500/600"
                      lazy-src="https://picsum.photos/200/300/?blur=10"
                    />
                  </div>
                </div>
                <br />
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </div>
        <br />
      </div>
    </div>
  </div>
</template>

<script>
import MainTitle from "../components/mainTitle.vue";
export default {
  name: "InspirePage",
  components: { MainTitle },
};
</script>
<style scoped>
.about-list-image-body {
  width: 160px;
  height: 160px;
  border-radius: 100%;
  border: solid;
}
.about-list-image-container {
  display: flex;
  justify-content: center;
}
.about-list-title {
  font-family: Permanent Marker;
  text-align: center;
}
.about-list-date {
  font-family: Ms Madi;
  font-size: 2rem;
}
.about-list-body-text {
  width: 90%;
  text-align: justify;
  font-family: Roboto;
}
.our-history {
  width: 100%;
  display: flex;
  align-items: center;
  flex-flow: column;
}
.about-us-container-text {
  width: 100%;
  display: flex;
  align-items: center;
  flex-flow: column;
}
.image-about-us {
  width: 200px;
  height: 200px;
  border-radius: 100%;
  border: solid;
}
.text-body-container {
  margin-top: 20px;
  display: flex;
  align-items: center;
  flex-flow: column;
}
.left {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.right {
  display: flex;
  align-items: center;
}
.history-text {
  border-top: 4px dashed;
  border-color: white !important;
  margin: 0;
  padding: 30px;
}

.history-text:nth-child(even) {
  border-left: 4px dashed;
  border-top-left-radius: 30px;
  border-bottom-left-radius: 30px;
  margin-right: 30px;
  padding-right: 0;
}

.history-text:nth-child(odd) {
  border-right: 4px dashed;
  border-top-right-radius: 30px;
  border-bottom-right-radius: 30px;
  margin-left: 30px;
  padding-left: 0;
}

.history-text:first-child {
  border-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}

.history-text:last-child {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.about-subtitle {
  color: #f2e9e4;
  font-family: "Permanent Marker";
  font-size: 2rem;
}
.about-container {
  padding: 20px;
}
.list- {
  width: 60%;
  text-align: justify;
  font-family: Robotos;
}
.cover {
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("assets/Coffee.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  object-fit: cover;
}
</style>
