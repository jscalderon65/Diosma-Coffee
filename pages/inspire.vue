<template>
  <div class="about-container animate__animated animate__fadeIn">
    <MainTitle text="Conoce un poco de nosotros" />
    <br />
    <div
      style="
        margin-top: 20px;
        display: flex;
        align-items: center;
        flex-flow: column;
      "
    >
      <div>
        <v-img
          style="width: 200px; height: 200px; border-radius: 100%"
          src="https://picsum.photos/500/600"
          lazy-src="https://picsum.photos/500/600"
        />
      </div>
      <br />
      <div
        style="
          width: 100%;
          display: flex;
          align-items: center;
          flex-flow: column;
        "
      >
        <h1 class="about-subtitle">¿Quienes somos?</h1>
        <br />
        <div
          class="about-body-text"
          style="width: 60%; text-align: justify; font-family: Roboto"
        >
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
      <div
        style="
          width: 100%;
          display: flex;
          align-items: center;
          flex-flow: column;
        "
      >
        <h1 class="about-subtitle">Nuestra historia</h1>
        <br />
        <div
          class="about-body-text"
          style="width: 90%; text-align: justify; font-family: Roboto"
        >
          <v-timeline :reverse="reverse" :dense="$vuetify.breakpoint.smAndDown">
            <v-timeline-item v-for="n in 4" :key="n" color="white">
              <span
                style="font-family: Ms Madi; font-size: 2rem"
                slot="opposite"
                >202{{ n }}</span
              >
              <v-card class="elevation-2">
                <v-card-title
                  style="font-family: Permanent Marker; text-align: center"
                >
                  Lorem ipsum
                </v-card-title>
                <v-card-text>
                  Lorem ipsum dolor sit amet, no nam oblique veritus. Commune
                  scaevola imperdiet nec ut, sed euismod convenire principes at.
                  Est et nobis iisque percipit, an vim zril disputando
                  voluptatibus, vix an salutandi sententiae.
                </v-card-text>
                <div style="display: flex; justify-content: center">
                  <div>
                    <v-img
                      style="width: 160px; height: 160px; border-radius: 100%"
                      src="https://picsum.photos/500/600"
                      lazy-src="https://picsum.photos/500/600"
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
.about-body-text {
}
.about-container {
  padding: 20px;
}
.cover {
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("assets/Coffee.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  object-fit: cover;
}
</style>
