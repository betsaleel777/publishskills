<template>
  <v-app light>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn @click.stop="miniVariant = !miniVariant" icon>
        <v-icon>mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}</v-icon>
      </v-btn>
      <v-btn @click.stop="clipped = !clipped" icon>
        <v-icon>mdi-application</v-icon>
      </v-btn>
      <v-btn @click.stop="fixed = !fixed" icon>
        <v-icon>mdi-minus</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
      <!-- <v-btn @click.stop="rightDrawer = !rightDrawer" icon>
        <v-icon>mdi-menu</v-icon>
      </v-btn> -->
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
    <!-- <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light>
              mdi-repeat
            </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->
    <v-footer :fixed="fixed" app>
      <v-row no-gutters>
        <v-col cols="4" class="text-center"
          ><v-chip class="ma-2" color="black" dark>
            <v-icon left>mdi-cellphone-android</v-icon>
            <strong>78-41-90-78 / 84-48-10-20</strong>
          </v-chip>
        </v-col>
        <v-col cols="4" class="text-center"
          ><v-chip class="ma-2" color="black" dark>
            <v-icon left>mdi-home</v-icon>
            <strong>Marcory / Cocody Mermoz</strong>
          </v-chip></v-col
        >
        <!-- <v-col cols="3">
          <v-chip class="ma-2" color="black" dark>
            <span>&copy; 2020</span>
          </v-chip>
        </v-col> -->
        <v-col cols="4" class="text-center">
          <v-chip class="ma-2" color="black" dark>
            <v-icon left>mdi-email</v-icon>
            <a
              class="mail"
              href="mailto:shin.ahoussou@gmail.com?subject=ENTRETIEN"
              >shin.ahoussou@gmail.com</a
            >
          </v-chip>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'AHOUSSOU JEAN-CHRIS ARNAUD'
    }
  }
}
</script>
<style scoped>
.mail {
  color: yellow;
}
</style>
