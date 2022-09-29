<template>
  <div class="main-container">
    <MainTitle text="!Donde encontrarnos!" />
    <br />
    <div class="info-container">
      <iframe
        :src="mapUrl"
        width="90%"
        height="300px"
        allowfullscreen=""
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
      ></iframe>
      <div @click="dialog = true" class="share-us-button-container">
        <MainButton text="¡Compartenos!" />
      </div>
    </div>
    <v-dialog v-model="dialog" width="500">
      <v-card>
        <v-card-title class="share-modal-title">
          <h1>¡Compartenos o recomiendanos!</h1>
          <br />
        </v-card-title>
        <br />
        <v-card-text>
          <div class="icons-share-container">
            <v-icon @click="sendThroughWhatsApp" class="icon-share"
              >mdi-whatsapp</v-icon
            >
          </div>
          <br />
          <div>
            <v-text-field
              filled
              append-outer-icon="mdi-content-copy"
              :value="inputCopyValue"
              @click:append-outer="copyText"
            ></v-text-field>
          </div>
          <v-alert
            v-if="confirmationCopy"
            class="animate__animated animate__fadeIn"
            outlined
            type="success"
            text
          >
            ¡Texto copiado correctamente!
          </v-alert>
          <v-alert
            v-if="confirmationShare"
            class="animate__animated animate__fadeIn"
            outlined
            color="pink"
            icon="mdi-heart"
            text
          >
            ¡Muchas gracias por compartirnos!
          </v-alert>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn @click="closeDialog"> Cerrar </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
import MainButton from "./mainButton.vue";
import MainTitle from "./mainTitle.vue";
export default {
  components: { MainButton, MainTitle },
  data() {
    return {
      dialog: false,
      inputCopyValue: window.location,
      mapUrl:
        "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3976.897714023442!2d-74.1518685860055!3d4.612323796649325!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8e3f9f218cd4cb51%3A0xd0b6373124abec96!2sDiosma%20caf%C3%A9!5e0!3m2!1ses-419!2sco!4v1664328832280!5m2!1ses-419!2sco",
      confirmationCopy: false,
      confirmationShare: false,
    };
  },
  methods: {
    closeDialog() {
      this.confirmationCopy = false;
      this.confirmationShare = false;
      this.dialog = false;
    },
    sendThroughWhatsApp() {
      window.open(`https://api.whatsapp.com/send?text=${window.location.href}`);
      this.confirmationShare = true;
      setTimeout(() => {
        this.closeDialog();
      }, 20000);
    },
    copyText() {
      navigator.clipboard.writeText(this.inputCopyValue);
      this.confirmationCopy = true;
      setTimeout(() => {
        this.closeDialog();
      }, 5000);
    },
  },
};
</script>

<style scoped>
iframe {
  border-radius: 10px;
  text-align: center;
  flex: 1;
}
.share-modal-title {
  font-family: Ms madi !important;
  display: flex;
  justify-content: center;
  width: 100%;
}
.icons-share-container {
  display: flex;
  justify-content: space-around;
}
.icon-share {
  cursor: pointer;
  font-size: 60px;
}
.info-container {
  flex: 1;
  width: 100%;
  display: flex;
  align-items: center;
  flex-flow: column;
}
.main-container {
  min-height: 100vh;
  height: auto;
  display: flex;
  flex-flow: column;
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("assets/Coffee.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
.share-us-button-container {
  width: 100%;
  flex: 1;
  display: flex;
  align-items: center;
  padding-top: 20px;
  padding-bottom: 20px;
}
</style>
