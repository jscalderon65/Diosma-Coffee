<template>
  <div>
    <div class="main-container">
      <div class="info-container animate__animated animate__fadeIn">
        <div class="info-title">
          <h1>¡Bienvenido!</h1>
        </div>
        <br />
        <div class="info-body">
          <blockquote class="stacked">
            <p>Una taza de café está llena de ideas</p>
          </blockquote>
        </div>
        <br />
        <MainButton
          :styleItems="'margin-top:40px'"
          text="Menú"
          :isRedirect="true"
          redirectPath="/menu"
        />
      </div>
    </div>
    <Gallery />
    <FindUs />
  </div>
</template>

<script>
import MainButton from "~/components/mainButton.vue";
import Gallery from "../components/gallery.vue";
import FindUs from "../components/findUs.vue";

export default {
  components: { Gallery, FindUs, MainButton },
  name: "IndexPage",
};
</script>
<style scoped>
.main-container {
  box-shadow: 2px 2px 2px 1px rgba(0, 0, 0, 0.2);
  color: #f2e9e4;
  min-height: 100vh;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("assets/Coffee.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}

.info-container {
  width: 100%;
  color: #f2e9e4;
  width: 300px;
  text-align: justify;
}

.title-font {
  font-family: Ms madi !important;
}

.info-title {
  margin-bottom: 10px;
  color: #f2e9e4;
  display: flex;
  justify-content: center;
  align-content: end;
  font-family: Ms madi;
  font-size: 2.5rem;
}

.info-body {
  color: #f2e9e4;
  font-family: "Permanent Marker";
  font-size: 2rem;
}
.stacked {
  text-align: center;
  padding: 20px 30px 20px 30px;
  border-radius: 5px;
  background: linear-gradient(to right, #f2e9e4 6px, transparent 6px) 0 0,
    linear-gradient(to right, #f2e9e4 6px, transparent 6px) 0 100%,
    linear-gradient(to left, #f2e9e4 6px, transparent 6px) 100% 0,
    linear-gradient(to left, #f2e9e4 6px, transparent 6px) 100% 100%,
    linear-gradient(to bottom, #f2e9e4 6px, transparent 6px) 0 0,
    linear-gradient(to bottom, #f2e9e4 6px, transparent 6px) 100% 0,
    linear-gradient(to top, #f2e9e4 6px, transparent 6px) 0 100%,
    linear-gradient(to top, #f2e9e4 6px, transparent 6px) 100% 100%;
  background-repeat: no-repeat;
  background-size: 20px 20px;
}
@media (max-width: 600px) {
  .info-title {
    font-size: 2rem;
  }
}
</style>
