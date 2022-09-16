<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title style="text-align: center" class="text-h5 animate__animated animate__fadeInLeft">
            <b style="font-family: Ms Madi; font-size: 2.5rem;color:#f2e9e4;">Diosma Café</b>
          </v-list-item-title>
          <!--           <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle> -->
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="item.to"
          @click="drawer = false"
        >
          <v-list-item-icon>
            <v-icon style="color:#f2e9e4;">{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title style="color:#f2e9e4;">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <div style="width: 100%; display: flex; justify-content: flex-end;">
        <div
          style="
            background: #f2e9e4;
            border: solid;
            height: 100px;
            width: 100px;
            display: flex;
            justify-content: center;
            align-items: flex-end;
            border-radius: 10px;
          "
        >
          <v-icon style="font-size: 4rem; color: black; margin-bottom: 5px"
            >mdi-coffee</v-icon
          >
        </div>
      </div>
    </v-app-bar>
    <v-main>
      <Nuxt />
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import Footer from "../components/footer";
export default {
  name: "DefaultLayout",
  components: { Footer },
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-home",
          title: "Inicio",
          to: "/",
        },
        {
          icon: "mdi-silverware",
          title: "Menú",
          to: "/menu",
        },
        {
          icon: "mdi-coffee",
          title: "Nosotros",
          to: "/inspire",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Diosma Coffee",
    };
  },
};
</script>
<style scoped>
/* b:before {
  content: "";
  display: block;
  width: 30px;
  height: 2px;
  background: white;
  position: absolute;
  left: 0;
  top: 50%;
  z-index: -2;
}
b:after {
  content: "";
  display: block;
  width: 30px;
  height: 2px;
  background: white;
  position: absolute;
  right: 0;
  top: 50%;
  z-index: -2;
} */

</style>