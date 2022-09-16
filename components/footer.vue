<template>
  <v-footer dark padless>
    <v-card dark style="width: 100vw" class="white--text text-center">
      <v-card-text>
        <v-btn v-for="icon in icons" :key="icon" class="mx-4 white--text" icon>
          <v-icon style="color:#f2e9e4;" size="30px">
            {{ icon }}
          </v-icon>
        </v-btn>
      </v-card-text>
    </v-card>
    <v-card dark style="width: 100vw" class="white--text text-center">
      <v-card-text dark >
        <b style="color:#f2e9e4;">© {{ new Date().getFullYear() }}</b> — <strong>Diosma Café, Derechos reservados</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      icons: ["mdi-facebook", "mdi-whatsapp", "mdi-gmail", "mdi-instagram"],
    };
  },
};
</script>

<style>
</style>