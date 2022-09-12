<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" :mini-variant="miniVariant" :clipped="clipped" fixed app>
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title style="text-align: center;" class="text-h5">
            <b>Diosma Café</b>
          </v-list-item-title>
          <!--           <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle> -->
        </v-list-item-content>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense nav>
        <v-list-item  v-for="item in items" :key="item.title" :to="item.to"  @click="drawer = false">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <div style="width: 100%;display:flex;justify-content: flex-end ;">
        <div
          style="border:solid;height:100px;width: 100px;background-color: aliceblue;display: flex;justify-content: center;align-items: flex-end;border-radius: 10px;">
          <v-icon style="font-size: 4rem;color: black;margin-bottom: 5px;">mdi-coffee</v-icon>
        </div>
      </div>
    </v-app-bar>
    <v-main>
      <Nuxt />
    </v-main>
    <v-footer dark padless>
      <v-card dark style="width: 100vw;" class="white--text text-center">
        <v-card-text>
          <v-btn v-for="icon in icons" :key="icon" class="mx-4 white--text" icon>
            <v-icon size="24px">
              {{ icon }}
            </v-icon>
          </v-btn>
        </v-card-text>
        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-silverware',
          title: 'Menú',
          to: '/'
        },
        {
          icon: 'mdi-coffee',
          title: 'Nosotros',
          to: '/inspire'
        }
      ],
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram',
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Diosma Coffee'
    }
  }
}
</script>
<style scoped>

</style>