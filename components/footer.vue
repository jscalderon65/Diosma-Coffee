<template>
  <v-footer dark padless>
    <v-card dark class="card-container white--text text-center">
      <v-card-text>
        <v-btn
          v-for="(social, index) in icons"
          :key="index"
          class="mx-4 white--text"
          icon
        >
          <a :href="social.redirect" target="_blank">
            <v-icon class="main-font-color" size="30px">
              {{ social.icon }}
            </v-icon>
          </a>
        </v-btn>
      </v-card-text>
    </v-card>
    <v-card dark class="card-container white--text text-center">
      <v-card-text dark>
        <b class="main-font-color">© {{ new Date().getFullYear() }}</b> —
        <b class="main-font-color">Diosma Café, Derechos reservados</b>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      icons: [
        /* "mdi-instagram" */
        /* "mdi-facebook" */ {
          icon: "mdi-whatsapp",
          redirect: "https://api.whatsapp.com/send?phone=3132496292",
        },
        {
          icon: "mdi-gmail",
          redirect: "mailto:diosmacafe@gmail.com",
        },
      ],
    };
  },
};
</script>

<style scoped>
.main-font-color {
  color: #f2e9e4;
}
.card-container {
  width: 100vw;
}
a {
  color: inherit !important;
  text-decoration: inherit;
}
</style>
