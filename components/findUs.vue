<template>
  <div class="main-container">
    <MainTitle text="!Donde encontrarnos!" />
    <br />
    <div
      style="
        flex: 4;
        display: flex;
        justify-content: start;
        align-items: center;
        flex-flow: column;
        width: 100%;
      "
    >
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3976.897714023442!2d-74.1518685860055!3d4.612323796649325!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8e3f9f218cd4cb51%3A0xd0b6373124abec96!2sDiosma%20caf%C3%A9!5e0!3m2!1ses-419!2sco!4v1664328832280!5m2!1ses-419!2sco"
        width="90%"
        height="80%"
        style="border-radius: 10px"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
      ></iframe>
      <div style="flex: 1; display: flex; align-items: center">
        <MainButton text="¡Compartenos!" />
      </div>
    </div>
  </div>
</template>

<script>
import MainButton from "./mainButton.vue";
import MainTitle from "./mainTitle.vue";
export default {
  components: { MainButton, MainTitle },
};
</script>

<style scoped>
.main-container {
  height: 100vh;
  display: flex;
  flex-flow: column;
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("assets/Coffee.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
</style>
