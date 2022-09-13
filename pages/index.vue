<template>
  <div class="main-container">
    <div class="info-container animate__animated animate__fadeIn">
      <div style="margin-bottom: 10px;" class="info-title">
        <h1>¡Bienvenido!</h1>
      </div>
      <div class="info-body">
        <blockquote class="stacked">
          <p>Una taza de café está llena de ideas</p>
        </blockquote>
      </div>
      <div style="text-align: center;margin-top: 40px;">
        <button class="green-button"><a href="/menu" class="manual-optin-trigger" data-optin-slug="atefh5rvxazforll">Menú</a></button>
      </div>
    </div>
  </div>
</template>

<script>
import VueArcText from "vue-arc-text";

export default {
  components: { VueArcText },
  name: "IndexPage",
};
</script>
<style scoped>
.main-container {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("assets/Coffee.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}

.info-container {
  margin-top: 20px;
  width: 300px;
  text-align: justify;
}

.title-font {
  font-family: Ms madi !important;
}

.info-title {
  display: flex;
  justify-content: center;
  align-content: end;
  font-family: Ms madi;
  font-size: 3rem;
}

.info-body {
  font-family: 'Permanent Marker';
  font-size: 2rem;
}
.stacked {
  text-align: center;
  border: solid 2px;
  padding: 20px 30px 20px 30px;
  border-radius: 5px;
  box-shadow: 13px 13px 0 0 white, 15px 15px 0 0 white, 15px 11px 0 0 white,
    11px 15px 0 0 white;
}
button.green-button{
  width: 50%;
  font-family: 'Permanent Marker';
  font-size: 1.5rem;
  padding: 7px 20px !important;
  border-radius: 5px;
  margin: 0px 0px 0px 20px;
  background-color: rgba(255,255,255,0);
  border: 3px solid white;
  border-radius: 5px;
  transition: 0.8s;
}

button.green-button a {
  text-decoration: none;
  color: #fff;
}

button.green-button:hover{
  background-color:  black;
  cursor: pointer;
 
}
button.green-button:hover a{
  color: white;
}
@media (max-width: 600px) {
  .info-title {
    font-size: 2rem;
  }

  .main-container {
    align-items: start;
  }

  .info-container {
    margin-top: 100px;
  }
}
</style>