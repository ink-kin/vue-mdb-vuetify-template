<template>
  <v-app id="app">
    <v-navigation-drawer
      v-model="drawer"
      app
      clipped
    >
      <v-img src="@/assets/Communication-Service-logo.png" />
      <v-list dense>
        <router-link to="/">
          <v-list-item link>
            <v-list-item-action>
              <v-icon>mdi-home</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>Маркетинговый отчёт</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <v-list-item link>
          <v-list-item-action>
            <v-icon @click="show1 = !show1">mdi-table</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title @click="show1 = !show1">Анализ</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <router-link :to="item.to" v-for="item in menuLiItemshow1" :key="item.title">
          <v-list-item link v-show="show1">
            <v-list-item-action>
              <v-icon>{{item.icon}}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{item.title}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <v-list-item link>
          <v-list-item-action>
            <v-icon @click="show2 = !show2">mdi-map</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title @click="show2 = !show2">Торги</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <router-link :to="item.to" v-for="item in menuLiItemshow2" :key="item.title">
          <v-list-item link v-show="show2">
            <v-list-item-action>
              <v-icon>{{item.icon}}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{item.title}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
        <v-list-item link>
          <v-list-item-action>
            <v-icon @click="show3 = !show3">mdi-chart-pie</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title @click="show3 = !show3">Медиа</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <router-link :to="item.to" v-for="item in menuLiItemshow3" :msg="item.title" :key="item.title">
          <v-list-item link v-show="show3">
            <v-list-item-action>
              <v-icon>{{item.icon}}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{item.title}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </router-link>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
      color="#fcb69f"
      dark
      src="https://picsum.photos/1920/1080?random"
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-toolbar-title>Маркетинговый отчёт фев.-окт. 2019 для Siempelkamp</v-toolbar-title>
      <v-spacer />
      <v-btn @click="show1 = !show1">
        <v-icon>mdi-magnify</v-icon>Анализ рынка
      </v-btn>
      <v-spacer />
      <v-btn @click="show2 = !show2">
        <v-icon>mdi-map</v-icon>Тогри
      </v-btn>
      <v-spacer />
      <v-btn @click="show3 = !show3">
        <v-icon>mdi-magnify</v-icon>Медиа
      </v-btn>
      <v-spacer />
    </v-app-bar>

    <v-content>
      <router-view/>
    <Footer />
    </v-content>
  </v-app>
</template>

<script>
import Footer from '@/components/Footer.vue'

export default {
  name: 'App',

  components: {
    Footer
  },
  props: {
    source: String,
  },
  data: () => ({
    drawer: null,
    show1: false,
    show2: false,
    show3: false,
    menuLiItemshow1: [
      {title: 'Анализ', icon: 'mdi-table', to: '/report'},
      {title: 'I 46.6', icon: 'mdi-table', to: '/report466'},
      {title: 'I 46.69.8', icon: 'mdi-table', to: '/report46_69_8'},
      {title: 'I 46.69.9', icon: 'mdi-table', to: '/report46_69_8'},
      {title: 'II 46.6', icon: 'mdi-table', to: '/report466'},
      {title: 'III 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '02 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '03 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '04 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '05 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '06 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '07 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '08 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '09 46.6', icon: 'mdi-table', to: '/report466'},
      {title: '10 46.6', icon: 'mdi-table', to: '/report466'},
      {title: 'I 28.2', icon: 'mdi-table', to: '/report466'},
      {title: 'II 28.2', icon: 'mdi-table', to: '/report466'},
      {title: 'III 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '02 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '03 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '04 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '05 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '06 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '07 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '08 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '09 28.2', icon: 'mdi-table', to: '/report466'},
      {title: '10 28.2', icon: 'mdi-table', to: '/report466'},
      {title: 'I 28.4', icon: 'mdi-table', to: '/report466'},
      {title: 'II 28.4', icon: 'mdi-table', to: '/report466'},
      {title: 'III 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '02 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '03 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '04 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '05 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '06 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '07 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '08 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '09 28.4', icon: 'mdi-table', to: '/report466'},
      {title: '10 28.4', icon: 'mdi-table', to: '/report466'},
      {title: 'I 43.2', icon: 'mdi-table', to: '/report466'},
      {title: 'II 43.2', icon: 'mdi-table', to: '/report466'},
      {title: 'III 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '02 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '03 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '04 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '05 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '06 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '07 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '08 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '09 43.2', icon: 'mdi-table', to: '/report466'},
      {title: '10 43.2', icon: 'mdi-table', to: '/report466'},
    ],
    menuLiItemshow2: [
      {title: 'Торги 46.6', icon: 'mdi-map', to: '/TorgTab466'},
      {title: 'Торги I 46.6', icon: 'mdi-map', to: '/TorgTab466I'},
      {title: 'Торги II 46.6', icon: 'mdi-map', to: '/TorgTab466II'},
      {title: 'Торги I 46.69', icon: 'mdi-map', to: '/TorgTab4669'},
      {title: 'Торги (46.66)', icon: 'mdi-map', to: '/TorgTab4666'},
      {title: 'Торги I 46.66', icon: 'mdi-map', to: '/TorgTab4666I'},
      {title: 'Торги II 46.66', icon: 'mdi-map', to: '/TorgTab4666II'},
      {title: 'Торги III 46.66', icon: 'mdi-map', to: '/TorgTab466III'},
      {title: 'Торги X 46.66', icon: 'mdi-map', to: '/TorgTab466X'},
      {title: 'Торги (46.6) 02.2019', icon: 'mdi-map', to: '/TorgTab466m02'},
      {title: 'Торги (46.6) 03.2019', icon: 'mdi-map', to: '/TorgTab466m03'},
      {title: 'Торги (46.6) 04.2019', icon: 'mdi-map', to: '/TorgTab466m04'},
      {title: 'Торги (46.6) 05.2019', icon: 'mdi-map', to: '/TorgTab466m05'},
      {title: 'Торги (46.6) 06.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (46.6) 07.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (46.6) 08.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (46.6) 09.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (46.6) 10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (46.6)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги 28.2', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 09.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 08.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 07.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 06.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 05.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 04.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 03.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) 02.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (46.6) 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) Мск МО СПб 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) свыше 10млн р 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 02.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 03.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 04.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 05.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 06.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 07.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 08.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 09.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.4) 10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (28.2) регионы 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 09.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 08.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 07.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 06.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 05.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 04.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 03.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) 02.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (43.2) свыше 5млн р 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (46.1) 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (46.1)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (46.1) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (46.1)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (46.1)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (46.1) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (46.1) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (46.1)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (46.1) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (52.29) 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (52.29) 01.02.2019 до 31.10.2019 расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (52.29)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (52.29) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (52.29)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (52.29) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (52.29)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (52.29) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (52.29)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (52.29) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (70.22) 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (70.22) 01.02.2019 до 31.10.2019 расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (70.22)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (70.22) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (70.22)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (70.22) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (70.22)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (70.22) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (70.22)', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (70.22) расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (71.1) свыше 5млн р 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (71.1) свыше 5млн р 01.02.2019 до 31.10.2019 расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (71.1) свыше 5млн р', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги I (71.1) свыше 5млн р расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (71.1) свыше 5млн р', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги II (71.1) свыше 5млн р расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (71.1) свыше 5млн р', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги III (71.1) свыше 5млн р расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (71.1) свыше 5млн р', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги X (71.1) свыше 5млн р расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (71.12) свыше 5млн р 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (71.12) свыше 5млн р 01.02.2019 до 31.10.2019расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (73.20) 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (73.20) 01.02.2019 до 31.10.2019 расширенный', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (82.99) 01.02.2019 до 31.10.2019', icon: 'mdi-map', to: '/Torg282'},
      {title: 'Торги (82.99) 01.02.2019 до 31.10.2019 расширенный', icon: 'mdi-map', to: '/Torg282'}
    ],
    menuLiItemshow3: [
      {title: 'Media Dashboard', icon: 'mdi-chart-pie', to: '/Brands'},
      {title: 'События', icon: 'mdi-chart-pie', to: '/profile'},
      {title: 'Media Tables', icon: 'mdi-chart-pie', to: '/media'},
      {title: 'Рейтинг Упоминаний', icon: 'mdi-chart-pie', to: '/Brands'},
    ]
  }),
  created () {
    this.$vuetify.theme.dark = true
  },
};
</script>
